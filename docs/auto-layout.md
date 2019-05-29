# AutoLayout

AutoLayout is a constraint based layout system that requires two things, **Size** and **Position**, in order to correctly position views.

## Size Classes
iOS uses **Size Classes** for applying **AutoLayout** constraints to be applied to the different devices. Using Size Classes you could define your views so that you could hide certain view or reposition them.

## AutoLayout with XCode
In XCode you have two buttons for applying the size and position of views, **Pin** and **Align**.
![Pin and Align][1]

## Resolving AutoLayout Issues
If the contraints are not satisfied, XCode will highlight the issues, and show either a red border around the view or a yello dotted line.
To resolve the issues, you have several options : 

- **Update Frames**: you think the red dotted lines are correct. Clicking this will move your layer to that position. 
- **Update Constraints**: you think that the red dotted lines are incorrect. Clicking this will change the constraints. 
- **Add Missing Constraint**: whatever is missing in term of position or size will be added.

![Resolve AutoLayout Issues][2]

## AutoLayout in Visual Studio

In Visual Studio, you switch the UI designer to AutoLayout mode by clicking the **Constraint Editing Mode** button.

![Switch constraint editing mode][3]

## Adding constraints

To add constraints to a view, switch to constraint editing mode, then use either the sizing or space constraints to add the constraint. You will notice dashed green lines as you get closer to the other views or the sides of the view controller. When all constraints are satisfied, you will notice solid blue lines.

![Add constraints][4]

[1]: /images/alignandpin.jpg
[2]: /images/autolayoutresolve.jpeg
[3]: /images/switch-constraint-editing.png
[4]: /images/constraint-handles.png