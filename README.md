package my_applet;
import java.awt.BorderLayout;
import java.awt.event.ItemEvent;
import java.awt.event.ItemListener;

import javax.swing.ButtonGroup;
import javax.swing.JButton;
import javax.swing.JCheckBox;
import javax.swing.JFrame;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;
import javax.swing.JPanel;
import javax.swing.JRadioButton;
import javax.swing.JScrollPane;
import javax.swing.JTextArea;
import javax.swing.JToggleButton;
import javax.swing.UIManager;
public class ChatFrame {
public static void main(String[] args) {
	try{
		UIManager.setLookAndFeel("javax.swing.plaf.nimbus.NimbusLookAndFeel");
	}
	catch(Exception e){
		e.printStackTrace();
		
	}
	JFrame frame = new JFrame("My Chat Frame");
	frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
	frame.setSize(400, 400);
	//Adding Menu
	JMenuBar menubar = new JMenuBar();
	JMenu fileMenu = new JMenu("File");
	JMenu helpMenu = new JMenu("Help");
	//adding menuItems 
	JMenuItem newItem = new JMenuItem("New");
	JMenuItem openItem = new JMenuItem("Open");
	//Adding into file menu
	fileMenu.add(newItem);
	fileMenu.add(openItem);
	menubar.add(fileMenu);
	menubar.add(helpMenu);
	//Adding button panel
	JPanel buttonPanel = new JPanel();
	JButton submitButton = new JButton("Submit");
	JButton resetButton  = new JButton("Reset");
	//Adding radio  buttons
	JRadioButton iiYearButton = new JRadioButton("II Year");
	JRadioButton iiiYearButton = new JRadioButton("III Year");
	ButtonGroup bg1 = new ButtonGroup();
	bg1.add(iiYearButton);
	bg1.add(iiiYearButton);
	buttonPanel.add(iiYearButton);
	buttonPanel.add(iiiYearButton);
	buttonPanel.add(submitButton);
	buttonPanel.add(resetButton);
	//Adding text area
	JTextArea textArea = new JTextArea();
	JScrollPane scrollPane = new JScrollPane(textArea);
	scrollPane.setHorizontalScrollBarPolicy(JScrollPane.HORIZONTAL_SCROLLBAR_ALWAYS);
	scrollPane.setVerticalScrollBarPolicy(JScrollPane.VERTICAL_SCROLLBAR_ALWAYS);
	//Adding toggle button
	JToggleButton toggleButton = new JToggleButton("On/Off");
	ItemListener itemListener = new ItemListener() {
		
		@Override
		public void itemStateChanged(ItemEvent itemEvent) {
			// TODO Auto-generated method stub
			int state = itemEvent.getStateChange();
			if(state == itemEvent.SELECTED){
				textArea.setEnabled(true);
			}else{
				textArea.setEnabled(false);
			}
		}
	};
	//Adding text to toggle button
	toggleButton.addItemListener(itemListener);
	//Adding check box panel
	JPanel chPanel = new JPanel();
	JCheckBox ch1 = new JCheckBox("C++");
	JCheckBox ch2 = new JCheckBox("Java",true);
	chPanel.add(ch1);
	chPanel.add(ch2);
	chPanel.add(toggleButton);
	frame.getContentPane().add(BorderLayout.PAGE_START,menubar);
	frame.getContentPane().add(BorderLayout.BEFORE_LINE_BEGINS,chPanel);
	frame.getContentPane().add(BorderLayout.CENTER,scrollPane);
	frame.getContentPane().add(BorderLayout.SOUTH,buttonPanel);
	
	frame.setVisible(true);
}













}
