import java.awt.*;
import java.awt.event.*;
class MenuDemo extends Frame implements ActionListener
{
public void menuDemo()
{
MenuBar mb=new MenuBar();
setMenuBar(mb);
MenuShortcut n=new MenuShortcut(KeyEvent.VK_N);
MenuShortcut o=new MenuShortcut(KeyEvent.VK_O);
MenuShortcut x=new MenuShortcut(KeyEvent.VK_X);
Menu filemenu=new Menu("File");
Menu editmenu=new Menu("Edit");
MenuItem newAction=new MenuItem("new",n);
MenuItem openAction=new MenuItem("open",o);
MenuItem exitAction=new MenuItem("exit",x);
MenuItem cutAction=new MenuItem("cut");
MenuItem copyAction=new MenuItem("copy");
MenuItem pasteAction=new MenuItem("paste");
newAction.addActionListener(this);
openAction.addActionListener(this);
exitAction.addActionListener(this);
filemenu.addSeparator();
filemenu.add(newAction);
filemenu.addSeparator();
filemenu.add(openAction);
filemenu.addSeparator();
filemenu.add(exitAction);
mb.add(filemenu);
cutAction.addActionListener(this);

copyAction.addActionListener(this);
pasteAction.addActionListener(this);
editmenu.add(cutAction);
editmenu.addSeparator();
editmenu.add(copyAction);
editmenu.addSeparator();
editmenu.add(pasteAction);
editmenu.addSeparator();
mb.add(editmenu);
addWindowListener(new WindowAdapter()

{
public void windowClosing(WindowEvent we)
{
System.exit(0);
}
});
}
public void actionPerformed(ActionEvent ae)
{
String action=ae.getActionCommand();
if(action.equals("new"))
{
System.out.println("new");
}
else if(action.equals("open"))
{
System.out.println("file");
}
else if(action.equals("exit"))
{
System.exit(0);
}
else if(action.equals("cut"))
{
System.out.println("cut");
}
else if(action.equals("copy"))
{
System.out.println("copy");
}
else if(action.equals("paste"))
{
System.out.println("paste");
}
}
public static void main(String[] poojitha)
{
MenuDemo md=new MenuDemo();
md.menuDemo();
md.setSize(500,500);
md.setTitle("Menu Demo");
md.setVisible(true);
}

}
