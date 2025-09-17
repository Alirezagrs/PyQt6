# Layout
### we used to show our widgets with .move() or .setGeometry() but if we want to have a responsive GUI thoese method will not be useful => with layout we create a responsive gui which user can resize the window without annihilating positions of widgets.

### QBoxLayout ==> the main class for layout but for using simple we will not use this lower class

### QVBoxLayout & QHBoxLayout => we use these classes which are inherited from QBoxLayout for vertical and horizental layout.

### exp:
    btn = QPushButton('btn') 
    main = QHBoxLayout()

    # add widget to layout
    main.addWidget(btn)
    
    # continue adding widgets to layout
    ...
    ...

    # custome widget
    widget = QWidget()

    # add layout to custom widget
    widget.setLayot(main)

    # now you can show widget with .move() or other ways like:
    self.setcentralWidget(widget)

## description of above xmp:
### when using layout no need touse parent for widgets because we are creating a custom widget ourselves that thoes widgets like button must go inside of. by QWidget() that is base class for other widgets(btn-label,...) we create a custome widget that contains layout.