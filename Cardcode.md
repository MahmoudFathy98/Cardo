//!!! Doctor Ayman ... i couldnt make a game so i just uploaded this as a part of challenge instead of ignoring it ... SORRY!!!
//_____________________________________________________________________________________________________________
public class card extends  JFrame implements MouseMotionListener , ActionListener
{
     private int mouseX;
     private int mouseY;
    //BufferedImage img = ImageIO.read(new File("D://CARDS//download.jpg"));
    MyPanel x = new MyPanel();
    JButton button = new JButton("Addcards");
    
    //JLabel picLabel = new JLabel(new ImageIcon(img));
    public card() throws IOException
    {
    setSize(1100,1100);
    setTitle("Cardygame");
    add(button , BorderLayout.PAGE_START);
    
     button.addActionListener(this);
     x.addMouseMotionListener(this);
     
     setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }
    public void actionPerformed(ActionEvent e)
    {
      //  button = (JButton)e.getSource();
       
       add(x);
       repaint();
    }
    public void mouseDragged(MouseEvent e) {
    mouseX = e.getX();
    mouseY = e.getY();
    x.setBounds(mouseX, mouseY,1000,550); repaint();}}
//_____________________________________________________________________________________________________________
//Class that creates an array of labels
public class MyPanel extends JPanel {
    public MyPanel() throws IOException{
        super(); 
        show();
    }

    private JLabel[] createLabels() throws IOException{
        JLabel[] labels=new JLabel[10];
        for (int i=0;i<10;i++){
            BufferedImage img = ImageIO.read(new File("D://CARDS//download.jpg"));
            labels[i]=new JLabel(new ImageIcon(img));
        }
        return labels;
    }

    private void show() throws IOException{
        JLabel[] lab=createLabels();
        for (int i=0;i<lab.length;i++){
            add(lab[i]);
        }
    }
}
//_____________________________________________________________________________________________________________
