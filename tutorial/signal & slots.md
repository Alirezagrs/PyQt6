# Signal & Slots   
### when you press a btn you expect sth happends so we can do it by signals(msg which are sent to slots(functions) when btn actions done like -> clicked - pressed - released) these 3 are signals.   
    
    class Mainwindow(QMainWindow):
        def __init__(self):
            super().__init__()
            self.setWindowTitle('title')
            # where the main window indicates
            self.setGeometry(x, y, weight, height)
            # or
            self.showFullScreen()
        

            self.btn = QPushButton()
            self.btn.setCheckacle(True)
            self.setCentralWidget(self.btn)
            self.btn.clicked.connect(self.btn_clicked)
            

            def btn_clicked(self, checked):
                # when clicking btn btn-text changed and btn got disable
                self.btn.setText('btn text')
                self.btn.setEnabled(False)


                if chcked:
                    ...
                else:
                    ...
        

    app = QApplication([]) # debut piont
    window = MainWindow()
    window.show()
    app.exec() # lunch

### self.setCentralWidget(self.btn) ==> it means after declaring btn where we can show it in the parent widget => center

###  self.btn.setCheckacle(True) ==> when you click a btn it goes down(checked = True) and when you release it coimming up (checked = False or unchecked) the res of it will pass to the slot as an argument