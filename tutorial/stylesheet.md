# QStyleFactory
### each computer has it is own style depends on os. for example we have Fusion for linux and Windows for windows. you can see the available styles your pc support:
    # mine ->[windows11,Windows,windowsvista,Fusion] 
    a = QStyleFactory.key()

    # you can change the default
    b = self.style().name() # mine -> windowsvista
    c = self.style("Fusion)
    
    
# you can use html and css:
    #html
    b = QPushButton("<p style="color:red;">click</p>")

    #css styles for diffrent stuffs
    b.setStyleSheet("""
    QPushButton{
        ...
    }
    QPushButton:hovet{
        ...
    }
    """)
  
