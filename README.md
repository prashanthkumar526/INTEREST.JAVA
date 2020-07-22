# INTEREST.JAVA
import javax.swing.*;
import javax.swing.event.*;
import java.awt.event.*;
import java.awt.*;
import java.lang.Math.*;
class InterestCalculator implements ActionListener
{
JFrame frame;
JPanel panel;
JLabel principleamount,time,rateofinterest,result;
JTextField textFieldforp,textFieldfort,textFieldforrate,textFieldforresult;
JButton buttonsimpleinterest,buttoncompoundinterest;
InterestCalculator()
{
frame=new JFrame("INTEREST CALCULATOR");
frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
frame.setSize(500,500);
frame.setLayout(new GridLayout());
frame.getContentPane().setBackground(Color.GREY);
panel=new JPanel();
panel.setBackground(Color.GREY);
principleamount=new JLabel("PRINCIPLE AMOUNT(p)");
principleamount.setSize(50,50);
panel.add(principleamount);
textFieldforp=new JTextField(10);
panel.add(textFieldforp);
time=new JLabel("TIME PERIOD(T)");
time.setSize(50,50);
panel.add(time);
textFieldfort=new JTextField(10);
panel.add(textFieldfort);
rateofintrest=new JLabel("RATE OF INTEREST(R)");
rateofintrest.setSize(50,50);
panel.add(rateofinterest);
textFieldforrate=new JTextField(10);
panel.add(textFieldforrate);
result=new JLabel("INTEREST RECEIVED");
result.setSize(50,50);
panel.add(result);
textFieldforresult=new JTextField(10);
panel.add(textFieldforresult);
buttonsimpleinterest=new JButton("SIMPLE INTEREST");
buttonsimpleinterest.addActionListener(this);
buttoncompoundinterest=new JButton("COMPOUND INTEREST");
buttoncompoundinterest.addActionListener(this);
panel.add(buttonsimpleinterest);
panel.add(buttoncompoundinterest);
frame.add(panel);
frame.setVisible(true);
}
public void actionPerformed(ActionEvent ae)
{
if(ae.getSource()==buttonsimpleinterest)
{
float p=Float.parseFloat(textFieldforp.getText());
float t=Float.parseFloat(textFieldfort.getText());
float r=Float.parseFloat(textFieldforrate.getText());
float answer=((p*t*r)/100);
textFieldforresult.setText(String.valueOf(answer));
}
if(ae.getSource()==buttoncompoundintrest)
{
double p=Double.parseDouble(textFieldforp.getText());
double t=Double.parseDouble(textFieldfort.getText());
double r=Double.parseDouble(textFieldforrate.getText());
double answer=(p * (Math.pow((1 +(r/100)),t))); 
textFieldforresult.setText(String.valueOf(answer));
}
}
}
class Interest
{
public static void main(String[] args)
{
InterestCalculator interestCalculator=new InterestCalculator();
}
}

