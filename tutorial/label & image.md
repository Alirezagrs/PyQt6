# Label
### you can use it for text and image
    l = QLabel('salam', parent)
    # or
    l = QLabel(parent)
    l.setText("salam")

    # font
    l.SetFont(QFont('Arial',size(px), ...))

    # style
    l.setStyleSheet("like css" => "color:red; bgcolor:blue; ...") 

    # alignment
    l.setAlignment(Qt.AlignmentFlag.AlignCenter)


### QLabel(text, parent) => you must detect the parent of widgets to be shown that is usually QMainWindow. then you can use setGeometry for that.

### l.setAlignment(Qt.AlignmentFlag.AlignCenter) ==>if you want to change the place of a widget according to it's background like padding , marging in css. we have lots of AlignmentFlag. even you can use many of alignments together :
    l.setAlignment(Qt.AlignmentFlag.AlignCenter | Qt.AlignmentFlag.AlignTop)

# Image
### to show images we need 2 clasees(widgets) QLabel and QPixmap

    l = QLabel(parent)
    p = QPixmap('image address')
    l.setPixmap(p)

### now the image is visible but => it does not have size and may be visible in a bad way(not completly obvious) ==> you can  use setGeometry() but still it may be shown with lack of size:
    l.setGeometry(..,..,..,..)
    l.setScaledContents(True)
### now with any size of label the picture is totally shown. If you wanted to show the real size of picture you have into window you can:
    l.setScaledContents(True)
    l.resize(p.width(), p.height())


### ***parent rules are for all widgets and .resize() for all widgets.

### .move(x, y) => instead of setGeometry you can use it that does not have weight and height and it is easier to use.

### l.setWordWrap(True) => it is used for text(label) when our text is so long you can use this to break the line, comming down to the new line.