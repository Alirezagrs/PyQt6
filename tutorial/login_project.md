# Points

### self.setMinimumSize(640, 426) => it means that a window like QMainWindow can not be smaller than this size. => max size for being the smallest
<br>

### context manager => always use it for things like opening a photo ... reminds me about memory management and \_\_del\_\_
    image = "./images/background_kingfisher.jpg"
    with open(image):
        main_label = QLabel(self)
        pixmap = QPixmap(image)
        main_label.setPixmap(pixmap)
        main_label.move(0, 0)
        main_label.resize(640, 426)

### self.setFixedSize(360, 220) => you can not change the size of the window anymore
<br>

### QMainWindow => you can have many of 'em to work with several windows if you want
<br>

### a = QLineEdit(paerent) => widget for input => for password field the value that user enters must not be seen so :
    a.setEchoMode(QLineEdit.EchoMode.Password)
    # makes * for values not seenable.
<br>

### cb = QCheckBox('text', parent) => a class for check box => signal of that is toggled that is determined if checked or not. and state of toggled will be passed to the func by argument:
    cb.toggled.connect(self.display_password_if_checked)

    # when checked is True show the normal password of user unless show the * for user entering the password -->

    def display_password_if_checked(self, checked):
        if checked:
            a.setEchoMode(QLineEdit.EchoMode.Normal)
        elif checked == False:
            a.setEchoMode(QLineEdit.EchoMode.Password)
<br>

### Events ==> these are special for OS like: mouse movement - clicking anywhere - clicking any btn - resize the window - close the window .... ===> actually events are lower-level than signals that for operation you should overwrite the event method of it. exp => when I close the main window a messagebox comes up and answer me for close: 
    # overwrite event for closing the main window
    def closeEvent(self, event):
        answer = QMessageBox.question(self, "title", "are u really want to close?", QMessageBox.StandardButton.No | QMessageBox.StandardButton.Yes, defaultButton=QMessageBox.StandardButton.No)

        if answer == QMessageBox.StandardButton.Yes:
            event.accept()
        if answer == QMessageBox.StandardButton.No:
            event.ignore()
<br>

### QMessageBox.StandardButton ==> btn for msg box, the  defaultButton arg is for the default btn when msg box comes up and it shows you which btn was chosen.
