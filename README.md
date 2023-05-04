Download Link: https://assignmentchef.com/product/solved-csci235-project-7-part-b-preparing-for-action-listener
<br>



Convert the main method of GraphCalc to a constructor so that you can pass an object of this class to other classes. Its main method then will simply create a window by calling the constructor as follows:

public static void main(String[] args) {

GraphCalc theWindow = new GraphCalc();

}




<strong>Task #1: Write a class that implements </strong><strong>ActionListener</strong><strong> for </strong><strong>Go</strong><strong> button.</strong>

The class will get inputs from the JTextFields in the window and verify them. For right now, you can simply print values from the text fields and the function’s value at the min <em>x</em> or max <em>x</em>. Add code for handling exceptions as well.




<strong>Task #2: Add code for drawing to the </strong><strong>ActionListener</strong><strong> class.</strong>

We learned that a Java class could implement multiple interfaces. Thus, your ActionListener class can implement Painter interface as well. The heading of the class will be as follows:




public class GoListener implements ActionListener, Painter { …




The above class then should implement actionPerformed and paint methods. If your class has an instance (object) of PaintPanel from GraphCalc, you may need to use the following statement for setting Painter:

<em>graphPanel</em>.setPainter(this);

where <em>graphPanel</em> is the instance of PaintPanel, and this indicates the current instance of GoListener.

<ul>

 <li>GoListener implements Painter as well, and thus, this works for the Painter object too.</li>

</ul>




The paint method should:

<ol>

 <li>Figure out the scale of graph so that you can associate pixels on the panel with points in the plane. For example, if the <em>x</em> range were -10 to 10, and the width of the panel were 200, the <em>x</em> value of -9 corresponds to the coordinate 10 on the vertical axis of the panel. With the same <em>y</em> range and the height of 200, the <em>y</em> value of -9 corresponds to the coordinate 190.</li>

 <li>If 0 is within the <em>x</em> range, draw the <em>y</em>-axis; if 0 is within the <em>y</em> range, draw the <em>x</em>-axis.</li>

 <li>Draw the curve. For each horizontal pixel coordinate,

  <ol>

   <li>Find the corresponding <em>x</em></li>

   <li>Find the value of the function at that <em>x</em> value: <em>f</em>(<em>x</em>). Use the Interpreter</li>

   <li>If the output value from the function is within the <em>y</em> range, fill in the pixel that corresponds to (<em>x</em>, <em>f</em>(<em>x</em>)) by drawing a filled rectangle of area 1 pixel.</li>

  </ol></li>

</ol>




Call repaint() on your PaintPanel (i.e., <em>graphPanel</em>.repaint()).