## PyQt

------

**Example code:** https://github.com/packtPublishing/Mastering-GUI-Programming-with-Python/tree/master

```bash
$pip install --user PyQt5
```

### Core Qt modules

- **QtCore** - low level data wrapper classes + utility functions + non-GUI functions
- **QtGui** - GUI-specific data wrapper classes
- **QtWidgets** - GUI widgets + layouts + high level GUI components 

### Hello Qt

```python
from PyQt5 import QtWidgets #the bulk of widget classes in QT

app = QtWidgets.QApplication([])
# widget creation
window = QtWidgets.QWidget(windowTitle='Hello Qt')
# show widget
window.show()
# begin the QApplication event loop
app.exec()
```

- **Widget:** visible componets of the GUI - buttons, etc.
- **QApplication:** object represents the state of the running application

### PyQt application template

```python
import sys
from PyQt5 import QtWidgets as qtw
from PyQt5 import QtGui as qtg
from PyQt5 import QtCore as qtc

class MainWindow(qtw.QWidget):

    def __init__(self):
        """MainWindow constructor.

        This widget will be our main window.
        We'll define all the UI components in here.
        """
        super().__init__()
        # Main UI code goes here

        # End main UI code
        self.show()


if __name__ == '__main__':
    app = qtw.QApplication(sys.argv)
    # it's required to save a reference to MainWindow.
    # if it goes out of scope, it will be destroyed.
    mw = MainWindow()
    sys.exit(app.exec())

```

**MainWindow class** is a subclass of QWidget + override the constructor method

- This is a good way to approach GUI building by customizing and expanding on Qt widget classes
- The constructor takes care of showing it self - self.show() 

**The main code execution**

- ```python
  if __name__ == '__main__':
  ```

  Allows us to inport this file and use the MainWindow class on other Python scrips by allowing this section to run only if this code is run directly.

- Passing sys.argv to QApplication() allows for functions like debugging and altering style
- Calling sys.exit(app.exec()) would allow for passing appropriate exit codes to the OS if the Qt instance crashes



### Placing and arranging widgets

1. Create layout object
2. Assign the layout object to the parent widget's layout property using setLayout() method
3. Add widgets to a layout using addWidget() method

**Note:** use **addLayout()** instead of **setLayout()** to add layouts to layout

#### Layout classes

- **Horizontal / Vertical Boxes** - QHBoxLayout / QVBoxLayout

  Divide the parent into horizontal or vertical boxes

  ```python
  def __init__(self):
          super().__init__()
  
          button1 = qtw.QPushButton("Push me", self, checkable=True, checked=True)
          button2 = qtw.QPushButton("Push me", self, checkable=True, checked=True)
          
          # Adding and setting layout
          layout = qtw.QVBoxLayout()
          self.setLayout(layout)
          
          # Adding Widgets
          layout.addWidget(button1)
          layout.addWidget(button2)
  ```

  

- **Grid Layout** - QGridLayout

  Arrange widgets in uniform rows and columns

  ```python
  def __init__(self):
      
          super().__init__()
          # Main UI code goes here
  
          button1 = qtw.QPushButton("Push me", self, checkable=True, checked=True)
          button2 = qtw.QPushButton("Push me", self, checkable=True, checked=True)
          
          layout = qtw.QGridLayout()
          self.setLayout(layout)
          
          layout.addWidget(button1, 0, 0)
          layout.addWidget(button2, 1, 1)
  ```



- **Form Layout** - QFormLayout

  When you need to have labels next to the input widgets

  ```python
  def __init__(self):
          super().__init__()
          # Main UI code goes here
  
          button1 = qtw.QPushButton("Push me", self, checkable=True, checked=True)
          button2 = qtw.QPushButton("Push me", self, checkable=True, checked=True)
          
          layout = qtw.QGridLayout()
          self.setLayout(layout)
          
          layout.addWidget(button1, 0, 0)
          layout.addWidget(button2, 0, 1)
          
          #adding a form layout to the grid layout
          form_layout = qtw.QFormLayout()
          layout.addLayout(form_layout, 1, 0)
  
          form_layout.addRow('Item 1', qtw.QLineEdit(self))
          form_layout.addRow(qtw.QLineEdit(self))
  ```



#### Controlling widget size

- Through pixels - it doesn't count for other things in the UI!

  ```python
  button1.setFixedSize(100, 20)
  ```

- Setting min & max size - more flexible 

  ```python
  button1.setMinimumSize(100, 20)
  button1.setMaximumSize(120, 40)
  ```

- Size hints & policies

  - Size hints: suggested size for a widget based on dynamic factors e.g. the length of its text. You can override it using Lambda functions:

    ```python
    textedit.sizeHint = Lambda : qtc.Qsize(500, 500)
    ```

  - Size policy: defines how to respond to size hints

    ```python
    textedit.setSizePolicy(
    	qtw.QSizePolicy.MinimumExpanding,
    )
    ```

  - Stretch factor: is an optional parameter for addWidget() that works only with QHBoxLayout and QVBoxLayout

    ```python
    layout.addWidget(qtw.QLineEdit('Long'), 2)
    # stretch factor of 2
    ```

    

#### Container Widgets

- **QTabWidget:** known as the notebook widget --> tabs
  1. Create ATabWidget object
  2. Build a UI page
  3. Add the page to the tab using QTabWidget.addTab() method
- **QGroupBox:** useful for grouping related input together