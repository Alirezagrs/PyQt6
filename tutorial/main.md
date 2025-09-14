# Widgets
### they are main elements that we can indicate users.we create a main widget as a window then creating small wifgets into it.

### first of all we should define a debut point

    class Mainwindow(QMainWindow):
        def __init__(self):
            super().__init__()
            self.setWindowTitle('title')

    app = QApplication([]) # debut piont
    window = MainWindow()
    window.show()
    app.exec() # lunch

### in  app = QApplication([]) the argument should come from cmd and we could put sys.argv in that if our program will be run from command line but we dont want to run it from cmd and dont have any sys.argv in here so put a [] for that.
### evry widget for showing needs a parent widget and will not show itself but with .show() we can show it. in this way each widget opens in one unique window