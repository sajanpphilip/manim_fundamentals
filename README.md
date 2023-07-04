# Manim Fundamentals
These are some tutorials which helps beginners (especially Mathematics Teachers) in Manim to start creating some basic animations. These tutorials are based on [Manim CE](https://docs.manim.community/).
Let's start learning about MObjects. Getting a grasp on MObjects will help you to create better animations.
## VMObjects

### 1. Lines
#### Example 1

```
%%manim -qm -v WARNING LineExample1

class LineExample1(Scene):
    def construct(self):

      line1=Line(1*RIGHT,1*LEFT)
      self.add(line1)
```
![LineExample1](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/b68b6967-39f1-4bab-9108-d8f3c684f441)

#### Example 2

```
%%manim -qm -v WARNING LineExample2

class LineExample2(Scene):
    def construct(self):

      line1=Line([0,0,0], [2,2,2])
      self.add(line1)
```
![LineExample2](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/7e5cb674-9814-453e-9c4c-99f7b7b38442)


#### Example 3

```
%%manim -qm -v WARNING LineExample3

class LineExample3(Scene):
    def construct(self):

      dot1=Dot(UP)
      dot2=Dot(DOWN)
      line=Line(dot1,dot2)
      self.add(dot1,dot2,line)
```
![LineExample3](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/5cdab846-394f-4ef9-8405-91a865306b88)

#### Exampel 4

```
%%manim -qm -v WARNING LineExample5

class LineExample5(Scene):
    def construct(self):

      circle1=Circle(radius=1).move_to(2*RIGHT)
      circle2=Circle(radius=2).move_to(2*LEFT)
      line=Line(circle1.get_center(),circle2.get_center())
      self.add(circle1,circle2,line)

````
![LineExample4](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/ed76c834-1b85-465c-824c-5889a85b61c1)



#### 1.1 Arrow
#### 1.2 Double Arrow
#### 1.3 Vector

   
