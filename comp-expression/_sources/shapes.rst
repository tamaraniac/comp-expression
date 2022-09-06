=======================================
Chapter 1: Shapes
=======================================

Section 1: Piet Mondrian
::::::::::::::::::::::::::
`Piet Mondrian <https://en.wikipedia.org/wiki/Piet_Mondrian>`_ was a Dutch artist known for his abstract art with simple geometric shapes in primary colors.

Here is a Snap program that generates random art like that of Piet Mondrian. You can find the `project here <https://snap.berkeley.edu/snap/snap.html#present:Username=shigure&ProjectName=Piet_Mondrian&editMode&noRun>`_ so you can play with it yourself, or download the picture of the code and drag that into your Snap project.

.. image:: figures/Piet_Mondrian-script-pic.png

This program generates images like this:

.. image:: figures/Piet-Mondrian-stage.png

Explaining the Snap program
---------------------------

The Processing Version
----------------------

.. activecode:: html1
   :language: html
   :nocodelens:

   <html>
       <script src="https://cdn.jsdelivr.net/npm/p5@1.4.1/lib/p5.js"></script>
   <body>
   <script>
       function setup(){
           createCanvas(500,500);
                      
            background(255);


            let r=random(25,475);
            let b=random(25,475);
            let h=random(245,475); 

            let myColors=[color('#ff0000'),color('#f0d200'),color('#0000fa'),color('#141414')]

            let randomcolorindex1 = Math.floor(random(0,3))
            let randomcolorindex2 = Math.floor(random(0,3))
            let randomcolorindex3 = Math.floor(random(0,3))
            let randomcolorindex4 = Math.floor(random(0,3))

           //1
			fill(myColors[randomcolorindex1])
			stroke(0)
			strokeWeight(10)
			rect(0,0,r,h)

			//2
			fill(myColors[randomcolorindex2]);
			stroke(0);
			strokeWeight(10);
			rect(((500-r)/2)+r,0,(500-r)/2,h);

			//3
			fill(myColors[randomcolorindex3]);
			stroke(0);
			strokeWeight(10);
			rect(0,h,b,500-h);

			//4
			fill(myColors[randomcolorindex4]);
			stroke(0);
			strokeWeight(10);
			rect(((500-b)/2)+b,h,(500-b)/2,500);

			noFill();
			stroke(0);
			strokeWeight(20);
			rect(0,0,500,500);

			noFill();
			stroke(0);
			strokeWeight(10);
			rect(0,0,500,h);
       }

    </script>
   </body>

   </html>

SECTION 2: Getting Started with Twine
::::::::::::::::::::::::::::::::::::::
