# Menu and Actions
### to create a navbar containing a menu like this vscode that there is a navbar at the top of if => File, edit, Selection .... exp:
    def createActions(self):
        self.new_act = QAction(QIcon("images/new_file.png"), "Quit")
        self.new_act.setShortcut("Ctrl+Q")
        self.new_act.triggered.connect(self.close)

    def createMenu(self):
        file = self.menuBar().addMenu("File")
        inside_field_of_file = file.addMenu("Preferences")
        file.add_addAction(self.new_act)
        file.addSeperator()
        file.add_addAction(another action)
        
        edit = self.menuBar().addMenu("Edit")
        tool = self.menuBar().addMenu("Selection")
    
## Description of above axp
### for creating a navbar we should use menuBar() and for each field use addMenu(). if you wanted to do sth like in Vscode => File - Preferences (in to in menu) you can do as above in file. each of this field of menu must do a thing when we click them so we handle it with actions. each action tells us when you click for example at File you see the action of it like Quit in here then you can set an icon befor quit with QIcon() and you can set a shortcut. if you want to have sth like signals in widgest you must use triggers.if you notice in File in vscode save all action is seperated from share action for doing such these in order to seperate actions of a field menu from each other use 
