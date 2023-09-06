# Typst v. LaTeX

I’ve started using Typst, which wants to replace LaTeX by being simpler, clearer, and with instant rendering.
Let’s compare them. 

Using LaTeX within Obsidian to write the quadratic formula, the output looks like this :
![[images/Pasted image 20230218220457.png]]

Using Typst’s online editor, we get this : 
![[images/Pasted image 20230218220611.png]]

Apart from the font, very similar, even indistinguishable ? No, even though it does require some pixel peeping, the square root is better drawn with Typst than in Obsidian :
![[images/Pasted image 20230218220853.png]]

But the real difference is in the writing experience. In natural keyboard language, this would look a bit like this :

`x = to (-b plusOrMinus sqrt(b^2 - 4ac)/2a)`

In LaTeX, this translates to

`$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}$$`

You’ve got to learn that $\pm$ is written `\pm`, remember that a fraction is `\over`, and use accolades for everything. 
Contrast this with the Typst syntax : 

`$ x = (-b plus.minus sqrt(b^2 - 4a) )/(2a) $`

More than that, it has syntactic coloration
![[images/Pasted image 20230218221455.png]]

And completion help : 
![[images/Pasted image 20230218221545.png]]

Typst is great and you should probably use it.