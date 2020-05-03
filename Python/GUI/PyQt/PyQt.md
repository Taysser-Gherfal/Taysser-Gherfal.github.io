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