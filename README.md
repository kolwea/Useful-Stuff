# Useful-Stuff

##Adding Css in Maven Project File
'''java
val f = File("src/main/resources/AppStylesheet.css")
scene.stylesheets.add("file:///" + f.absolutePath.replace("\\", "/"))
'''
