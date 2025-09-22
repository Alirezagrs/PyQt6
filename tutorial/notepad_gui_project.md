# t = QTextEdit()
### exactly text area in html. a big text input for wrting

### t.clear() => will be cleared the text of it

### other methods
    # these methods are same with QLineEdit
    t.undo()    # ctrl + z
    t.redo()    # ctrl + y
    t.cut()     # ctrl + x
    t.copy()    # ctrl + c
    t.paste()   # ctrl + v
    t.currrentFont() # getting the font of it
    t.setCurrentFont(font) # replacing a font
    t.setTextBackgroundColor(color) # changing bg color


# QFileDialog.getOpenFileName
### if a user wants to pick a file from his/her system to do sth with.like chossing a file load the text of it into a QTextEdit or after creating text in QTextEdit save it to a new file:
    # how change text of QTextEdit
    a, _ = QFileDialog.getOpenFileName(
        self, # parent
        "Open File", # title of the page opening
        "", 
        "HTML Files (*.html);;Text Files (*.txt)"
    )
    if a:
        with open(a, 'r') as f:
        c = f.read()
    t.setText(y)

### what is "" in above => the route which you say to be opend when it pops up if "" => will open at your project route

### the last arg is the pattern for filter files you want to find in the pop up window.

# QFileDialog.getSaveFileName
### arguments of it like above and this is for save new files like you have modified text of a QTextEdit and want to save to a new file:
    file_name, _ = QFileDialog.getSaveFileName(self, "Save File", "", "HTML Files (*.html);;Text Files (*.txt)")

    if file_name.endswith(".txt"):
        notepad_text = self.text_edit.toPlainText()
        with open(file_name, "w") as f:
            f.write(notepad_text)
    elif file_name.endswith(".html"):
        notepad_html = self.text_edit.toHtml()
        with open(file_name, "w") as f:
            f.write(notepad_html)

### in above in depends on the format of our text if we want to save a *.txt so we must save it as a plaintext(normal text) or if it would be html must be Html format

# QFontDialog.getFont
### if a user wants to choose a font for it's program:
    current = self.text_edit.currentFont()
    font, ok = QFontDialog.getFont(current, self, options=QFontDialog.FontDialogOption.DontUseNativeDialog)
        if ok:
            self.text_edit.setCurrentFont(font)

### description of above => if a user chose a font and press ok of the pop up window, the chosen font will go in font argument and ok=True but if pick a font but and got regret of choosing and pressing cancle in the pop up, again the font arg is chosen font and ok=False. so important point ====>>>>!!!! by default it is using our system font that might be unknown to QT so we must use QT fonts:
    options=QFontDialog.FontDialogOption.DontUseNativeDialog

# QColorDialog.getColor()
### choose the favorite color by user to use in the program.
    color = QColorDialog.getColor()
    if color.isValid():
        self.text_edit.setTextBackgroundColor(color)