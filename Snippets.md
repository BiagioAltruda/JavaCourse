#### javax.swing.* notes
https://docs.oracle.com/javase/8/docs/api/javax/swing/package-summary.html

Per creare un frame in java:
```
import javax.swing.JFrame;

public class MyFrame {
	public static void main(String[] args){

	//Creazione della finestra
	JFrame frame = new JFrame("A Frame");

	//Settare le dimensioni
	frame.setSize (500,500);

	//Comportamento alla chiusura
	frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

	//Rendere il frame visibile
	frame.setVisible(true);
	}
}
```

Per creare un bottone invece:
```
...
JButton button = new JButton("TEXT");

//Aggiungi il bottone al frame
frame.getContentPane().add(button);

frame.setVisibile(true);
...
```