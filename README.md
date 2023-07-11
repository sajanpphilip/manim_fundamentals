# Manim Fundamentals
These are some tutorials which helps beginners (especially Mathematics Teachers) in Manim to start creating some basic animations. These tutorials are based on [Manim CE](https://docs.manim.community/).
Let's start learning about VMObjects. Getting a grasp on VMObjects will help you to create better animations. I have used Google Colab to bypass the Installation steps for Manim. These are very basic tutorials for beginners. For Advanced users, please refer Manim Documentation.

## [Basic VMobjects](#Basic-VMobjects)
###    [1. Lines](#1.-Lines)
###        [Example 1](#Example_1)

## Basic VMObjects

## 1. Lines
### Example 1

```
%%manim -qm -v WARNING LineExample1

class LineExample1(Scene):
    def construct(self):

      line1=Line(1*RIGHT,1*LEFT)
      self.add(line1)
```
![LineExample1](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/b68b6967-39f1-4bab-9108-d8f3c684f441)

### Example 2

```
%%manim -qm -v WARNING LineExample2

class LineExample2(Scene):
    def construct(self):

      line1=Line([0,0,0], [2,2,2])
      self.add(line1)
```
![LineExample2](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/7e5cb674-9814-453e-9c4c-99f7b7b38442)


### Example 3

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

### Exampele 4

```
%%manim -qm -v WARNING LineExample4

class LineExample4(Scene):
    def construct(self):

      circle1=Circle(radius=1).move_to(2*RIGHT)
      circle2=Circle(radius=2).move_to(2*LEFT)
      line=Line(circle1.get_center(),circle2.get_center())
      self.add(circle1,circle2,line)

````
![LineExample4](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/ed76c834-1b85-465c-824c-5889a85b61c1) 

### Line Example 5

```
%%manim -qm -v WARNING LineExample5

class LineExample5(Scene):
    def construct(self):

      dot1=Dot(UP)
      dot2=Dot(DOWN)
      dot3=Dot(2*RIGHT, color = RED)
      line=Line(dot1,dot2)
      proj_point = line.get_projection(dot3.get_center()) # dot3.get_center() is used to get the exact coordinate
      dot4= Dot(proj_point, color = RED)
      proj_line = Line(dot3.get_center(),proj_point, color = BLUE)
      self.add(dot1,dot2,dot3,dot4,line,proj_line)

```
![Example 5](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/21e0fcf9-86ce-4695-85fb-a5bf6f903341)

### Line Example 6

```
%%manim -qm -v WARNING LineExample6

class LineExample6(Scene):
    def construct(self):

      square1=Square(side_length = 2.0, color = RED).shift(2*RIGHT)
      square2=Square(side_length = 1.0, color = BLUE).shift(2*LEFT)
      line=Line(square1.get_corner(UR),square2.get_edge_center(DOWN))
      self.add(square1,square2,line)

```
![Example 6](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/f116f199-1068-4a47-a952-7cc6b874e575)


### Line Example 7

```
%%manim -qm -v WARNING LineExample7

class LineExample7(Scene):
    def construct(self):

      line1 = Line()
      line2 = Line()
      line3 = Line()
      line4 = Line()
      lines = VGroup(line1, line2, line3, line4).arrange(DOWN, buff=1)
      self.add(lines)
```
![Example 7](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/8fe125c1-6977-4400-873d-eec82a8b3dc0)

### Line Example 8

```
%%manim -qm -v WARNING LineExample8

class LineExample8(Scene):
    def construct(self):

      line1 = Line(color = PURPLE, stroke_width = 40)
      line2 = Line(color = BLUE_D, stroke_width = 40)
      line3 = Line(color = BLUE_C,stroke_width = 40)
      line4 = Line(color = GREEN_D, stroke_width = 40)
      line5 = Line(color = YELLOW_C, stroke_width = 40)
      line6 = Line(color = GOLD, stroke_width = 40)
      line7 = Line (color = RED, stroke_width = 40)
      lines = VGroup(line1, line2, line3, line4, line5, line6,line7).arrange(DOWN, buff = 0.4)
      self.add(lines)
```
![Example 8](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/cc53d50d-4941-4561-84e6-14995338ff25)

  
## 1.1 Dashed Lines
### Example 1
```
%%manim -qm -v WARNING DashedLineExample1 

class DashedLineExample1(Scene):
    def construct(self):

      dashed_line1 = DashedLine(2*UL, 2*UR)
      dashed_line2 = DashedLine(2*LEFT, 2*RIGHT, dash_length = 0.5)      
      dashed_line3 = DashedLine(2*DL, 2*DR, dash_length = 0.5, dashed_ratio = 0.9)
      dashed_line4 = DashedLine(dashed_line1.get_end(),dashed_line2.get_start())
      dashed_line5 = DashedLine(dashed_line2.get_last_handle(), dashed_line3.get_first_handle())


      self.add(dashed_line1, dashed_line2, dashed_line3,dashed_line4, dashed_line5)
```
![Dashed_Line Example 1](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/d7ad2f0e-84c3-4067-a67b-00f01f8bb477)





## 1.2 Arrow
### Example 1 

```
%%manim -qm -v WARNING ArrowExample1 

class ArrowExample1(Scene):
   def construct(self):

      arrow1 = Arrow(stroke_width=5, buff=0.1, max_tip_length_to_length_ratio=0.1, max_stroke_width_to_length_ratio=5, start=UL, end = UR, color = RED)
      arrow2 = Arrow(stroke_width=10, buff=0.2, max_tip_length_to_length_ratio=0.25, max_stroke_width_to_length_ratio=10, start = LEFT, end = RIGHT, color = BLUE)
      arrow3 = Arrow(stroke_width=20, buff=0.4, max_tip_length_to_length_ratio=0.5, max_stroke_width_to_length_ratio=20, start = DL, end = DR, color = GREEN)
      

      self.add(arrow1, arrow2, arrow3)
```
![Arrow](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/3368c97b-2071-494f-b016-d4a383bc73a6)

## 1.3 Double Arrow
### Example 1
```
%%manim -qm -v WARNING DoubleArrowExample1 

class DoubleArrowExample1(Scene):
   def construct(self):

      double_arrow1 = DoubleArrow(stroke_width=5, buff=0.1, max_tip_length_to_length_ratio=0.1, max_stroke_width_to_length_ratio=5, start=UL, end = UR, color = RED)
      double_arrow2 = DoubleArrow(stroke_width=10, buff=0.2, max_tip_length_to_length_ratio=0.25, max_stroke_width_to_length_ratio=10, start = LEFT, end = RIGHT, color = BLUE)
      double_arrow3 = DoubleArrow(stroke_width=20, buff=0.4, max_tip_length_to_length_ratio=0.5, max_stroke_width_to_length_ratio=20, start = DL, end = DR, color = GREEN)
      

      self.add(double_arrow1, double_arrow2, double_arrow3)
```
![doublearrow](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/c719d7e1-659b-4ce9-bd99-a436b57cfb15)

## 1.4 Tangent Line
### Example 1

```
%%manim -qm -v WARNING TangentLineExample1 

class TangentLineExample1(Scene):
    def construct(self):
      
        circle = Circle(radius=3)
        line_1 = TangentLine(circle, alpha = 0.0, length = 5, color=RED) 
        line_2 = TangentLine(circle, alpha = 0.25, length = 5, color=BLUE)
        line_3 = TangentLine(circle, alpha = 0.5, length = 5, color = GREEN) 
        line_4 = TangentLine(circle, alpha = 0.75, length = 5, color = YELLOW) 

        self.add(circle, line_1, line_2, line_3, line_4)
```
![Tangent Line](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/86620eaa-be69-4dec-8cdc-73d973daa0c7)

## 2. Arc
### Example 1

```
%%manim -qm -v WARNING ArcExample1 

class ArcExample1(Scene):
    def construct(self):
        arc1 = Arc(radius=1.0, start_angle=0, angle = 3*PI/4.0, num_components=15, arc_center=2*RIGHT)
        line1= Line(arc1.get_center(), arc1.get_start(), color = YELLOW)
        line2 = Line(arc1.get_center(), arc1.get_end(), color = BLUE)
        

        self.add(arc1,line1, line2)
```

![arc](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/ca1b96ce-5df2-4569-914d-ea4757d1b76a)

## 2.1 Circle
### Example 1

```
%%manim -qm -v WARNING CircleExample1

class CircleExample1(Scene):
    def construct(self):
      
        circle_1 = Circle(radius=1.0, color = BLUE).move_to(2*RIGHT)
        circle_2 = Circle(radius=1.5, color=RED).next_to(circle_1, buff=0.5)
        circle_3 = Circle(radius=1.0, color=GOLD, fill_opacity=0.5)
        circle_4 = Circle(radius = 0.5, color = WHITE)
        circle_5 = Circle(radius = 0.5, color = GREEN)
        circle_6 = Circle(radius = 0.5, color = PURPLE)
        circle_7 = Circle.from_three_points(2*LEFT,2*DOWN,1*LEFT)
        circ_group = Group(circle_4, circle_5, circle_6).arrange(buff=0.5).move_to(2*UP)


        self.add(circle_1, circle_2, circle_3, circle_4, circ_group, circle_7)
```
![circle](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/a866d6ff-8538-4edb-80ae-b421a4167b31)

### Example 2

```
%%manim -qm -v WARNING CircleExample2

class CircleExample2(Scene):
    def construct(self):
      
        circle_1 = Circle(radius=3.0, color = BLUE).move_to(2*RIGHT)
        p1 = circle_1.point_at_angle(PI/2.0)
        p2 = circle_1.point_at_angle(3*PI/2.0)
        p3 = circle_1.point_at_angle(PI)
        p4 = circle_1.point_at_angle(0)
        line1 = Line(p1,p2, color = RED)
        line2 = Line(p3,p4, color = GREEN)

        self.add(circle_1, line1, line2)
```
![circle 2](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/a1b05d9e-69d3-4b83-a1fa-7ad3d5f157c3)

### Example 3

```
%%manim -qm -v WARNING CircleExample3

class CircleExample3(Scene):
    def construct(self):

      triangle1 = Triangle (color = RED).move_to(5*LEFT)
      circle_1 = Circle(color = WHITE).surround(triangle1,buffer_factor=1.5)
      triangle2 = Triangle (color= BLUE).move_to(2*LEFT)
      circle_2 = Circle(color = GREEN).surround(triangle2,buffer_factor = 0.25)
      line = Line(0.5*LEFT, 0.5*RIGHT)
      circle_3 = Circle(color = GOLD).surround(line)
      square1 = Square(side_length=1.0).move_to(2*RIGHT)
      circle_4 = Circle(color = BLUE).surround(square1,buffer_factor=1.5)
      square2 = Square(side_length=1.0).move_to(5*RIGHT)
      circle_5 = Circle(color = YELLOW).surround(square2,buffer_factor=0.25)

      self.add(triangle1, triangle2, line, square1, square2, circle_1, circle_2, circle_3, circle_4, circle_5)
```

![circle 3](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/a75c12eb-0d9a-4794-9770-aba775b65f01)
## 2.2 Ellipse

### Example 1
```
%%manim -qm -v WARNING EllipseExample1

class EllipseExample1(Scene):
    def construct(self):
        ellipse_1 = Ellipse(width=2.0, height=4.0, color=RED,).move_to(2*LEFT)
        ellipse_2 = Ellipse(width=4.0, height=3.0, color=BLUE, fill_color= BLUE, fill_opacity = 0.5).move_to(2*UR)
        
        self.add(ellipse_1,ellipse_2)
```
![ellipse example](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/4cfd6599-b383-417b-88ed-1e875a07c8ba)


## 2.3 ArcBetweenPoints

### Example 1
```
%%manim -qm -v WARNING ArcBetweenPointsExample1

class ArcBetweenPointsExample1(Scene):
    def construct(self):
      arc1=ArcBetweenPoints(start = 2.0*RIGHT, end = 2.0*UP, stroke_color = RED, stroke_width = 2.0)
      arc2=ArcBetweenPoints(start = 3.0*LEFT, end = ORIGIN, stroke_color = BLUE)
      arc3=ArcBetweenPoints(start = 1.0*UP, end = 1.0*LEFT,radius=7.0, color = GREEN)
      arc4 = ArcBetweenPoints(start = 1*RIGHT, end = 2.5*UP, angle = 3.14, color = PURPLE)
      self.add(arc1,arc2,arc3,arc4)
```

![arcpoints](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/f3d75bdf-18e8-4929-8f71-292b6df00067)

## 2.4 CurvedArrow

### Example 1
```
%%manim -qm -v WARNING CurvedArrowExample1

class CurvedArrowExample1(Scene):
   def construct(self):

      c_arrow1 = CurvedArrow(stroke_width=5,start_point=UL, end_point = UR, color = RED)
      c_arrow2 = CurvedArrow(stroke_width=10,start_point = LEFT, end_point = RIGHT, color = BLUE)
      c_arrow3 = CurvedArrow(stroke_width=20, start_point = DL, end_point = DR, color = GREEN)


      self.add(c_arrow1, c_arrow2, c_arrow3)
```
![carrow](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/e3a2339e-3596-4cc9-b0b7-f245e738a7af)

## 2.5 CurvedDoubleArrow

```
%%manim -qm -v WARNING CurvedDoubleArrowExample1

class CurvedDoubleArrowExample1(Scene):
   def construct(self):

      cd_arrow1 = CurvedDoubleArrow(stroke_width=5,start_point=UL, end_point = UR, color = RED)
      cd_arrow2 = CurvedDoubleArrow(stroke_width=10,start_point = LEFT, end_point = RIGHT, color = BLUE)
      cd_arrow3 = CurvedDoubleArrow(stroke_width=20, start_point = DL, end_point = DR, color = GREEN)


      self.add(cd_arrow1, cd_arrow2, cd_arrow3)
```

 ![cdarrow](https://github.com/sajanpphilip/manim_fundamentals/assets/104676396/042a7ed8-7deb-4715-ab09-99f60da52e8b)
  
