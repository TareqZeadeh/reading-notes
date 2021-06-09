# CSS Transforms
### With CSS3 came new ways to position and alter elements. Now general layout techniques can be revisited with alternative ways to size, position, and change elements. All of these new techniques are made possible by the transform property.

#### The transform property comes in two different settings, two-dimensional and three-dimensional. Each of these come with their own individual properties and values.

## Transform Syntax (#transform-syntax)
#### The actual syntax for the transform property is quite simple, including the transform property followed by the value. The value specifies the transform type followed by a specific amount inside parentheses.
```
 div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
} 
```

## 2D Transforms (#two-dimensional-transfor)
#### Elements may be distorted, or transformed, on both a two-dimensional plane or a three-dimensional plane.
#### Two-dimensional transforms work on the x and y axes, known as horizontal and vertical axes. Three-dimensional transforms work on both the x and y axes, as well as the z axis. 
#### These three-dimensional transforms help define not only the length and width of an element, but also the depth.
### 2D Rotate:
#### The transform property accepts a handful of different values. The rotate value provides the ability to rotate an element from 0 to 360 degrees.
#### Using a positive value will rotate an element clockwise, and using a negative value will rotate the element counterclockwise. The default point of rotation is the center of the element, 50% 50%, both horizontally and vertically. 

### 2D Scale:
#### Using the scale value within the transform property allows you to change the appeared size of an element. 
#### The default scale value is 1, therefore any value between .99 and .01 makes an element appear smaller while any value greater than or equal to 1.01 makes an element appear larger.

### 2D Translate:
#### The translate value works a bit like that of relative positioning, pushing and pulling an element in different directions without interrupting the normal flow of the document.
#### Using the translateX value will change the position of an element on the horizontal axis while using the translateY value will change the position of an element on the vertical axis.
### 2D Skew:
#### The last transform value in the group, skew, is used to distort elements on the horizontal axis, vertical axis, or both.
#### The syntax is very similar to that of the scale and translate values. Using the skewX value distorts an element on the horizontal axis while the skewY value distorts an element on the vertical axis. To distort an element on both axes the skew value is used, declaring the x axis value first, followed by a comma, and then the y axis value.
### Combining Transforms (#combining-transforms):
#### It is common for multiple transforms to be used at once, rotating and scaling the size of an element at the same time for example. 
#### n this event multiple transforms can be combined together. To combine transforms, list the transform values within the transform property one after the other without the use of commas.


### Transform Origin (#transform-origin):
#### As previously mentioned, the default transform origin is the dead center of an element, both 50% horizontally and 50% vertically. To change this default origin position the transform-origin property may be used.
#### The transform-origin property can accept one or two values. When only one value is specified, that value is used for both the horizontal and vertical axes. If two values are specified, the first is used for the horizontal axis and the second is used for the vertical axis.


### Perspective (#perspective):
#### In order for three-dimensional transforms to work the elements need a perspective from which to transform. The perspective for each element can be thought of as a vanishing point, similar to that which can be seen in three-dimensional drawings.
#### The perspective of an element can be set in two different ways. One way includes using the perspective value within the transform property on individual elements, while the other includes using the perspective property on the parent element residing over child elements being transformed.

## 3D Transforms (#three-dimensional-transforms):
### 3D Rotate:
#### With three-dimensional transforms we can rotate an element around any axes. To do so, we use three new transform values, including rotateX, rotateY, and rotateZ.
#### Using the rotateX value allows you to rotate an element around the x axis, as if it were being bent in half horizontally. Using the rotateY value allows you to rotate an element around the y axis, as if it were being bent in half vertically. Lastly, using the rotateZ value allows an element to be rotated around the z axis.

### 3D Scale:
#### By using the scaleZ three-dimensional transform elements may be scaled on the z axis. 
#### This isn’t extremely exciting when no other three-dimensional transforms are in place, as there is nothing in particular to scale.



### 3D Translate:
#### Elements may also be translated on the z axis using the translateZ value. A negative value here will push an element further away on the z axis, resulting in a smaller element.
#### Using a positive value will pull an element closer on the z axis, resulting in a larger elemen






### 3D Skew:
#### Skew is the one two-dimensional transform that cannot be transformed on a three-dimensional scale. 
#### Elements may be skewed on the x and y axis, then transformed three-dimensionally as wished, but they cannot be skewed on the z axis.







### Shorthand 3D Transforms:
#### As with combining two-dimensional transforms, there are also properties to write out shorthand three-dimensional transforms.
#### These properties include rotate3d, scale3d, transition3d, and matrix3d. These properties do require a bit more math, as well as a strong understanding of the matrices behind each transform.







### Transform Style (#transform-style):
#### On occasion three-dimensional transforms will be applied on an element that is nested within a parent element which is also being transformed.
#### To allow nested elements to transform in their own three-dimensional plane use the transform-style property with the preserve-3d value.








### Backface Visibility (#backface-visibility):
#### When working with three-dimensional transforms, elements will occasionally be transformed in a way that causes them to face away from the screen. 
#### This may be caused by setting the rotateY(180deg) value for example. By default these elements are shown from the back. So if you prefer not to see these elements at all, set the backface-visibility property to hidden, and you will hide the element whenever it is facing away from the screen. 



# Transitions & Animations
### With CSS3 transitions you have the potential to alter the appearance and behavior of an element whenever a state change occurs, such as when it is hovered over, focused on, active, or targeted.
### Animations within CSS3 allow the appearance and behavior of an element to be altered in multiple keyframes. Transitions provide a change from one state to another, while animations can set multiple points of transition upon different keyframes.


### Transitions(#transitions):
#### As mentioned, for a transition to take place, an element must have a change in state, and different styles must be identified for each state
#### The easiest way for determining styles for different states is by using the(:hover, :focus, :active, and :target) pseudo-classes.





### Transitional Property:
#### The transition-property property determines exactly what properties will be altered in conjunction with the other transitional properties.
#### By default, all of the properties within an element’s different states will be altered upon change. However, only the properties identified within the transition-property value will be affected by any transitions.





### Transitional Properties:
#### t is important to note, not all properties may be transitioned, only properties that have an identifiable halfway point. 
#### Colors, font sizes, and the alike may be transitioned from one value to another as they have recognizable values in-between one another. The display property, for example, may not be transitioned as it does not have any midpoint. 








### Transition Duration:
#### The duration in which a transition takes place is set using the transition-duration property.
#### The value of this property can be set using general timing values, including seconds (s) and milliseconds (ms). These timing values may also come in fractional measurements, .2s for example.








### Transition Timing:
#### The transition-timing-function property is used to set the speed in which a transition will move.
#### Knowing the duration from the transition-duration property a transition can have multiple speeds within a single duration. A few of the more popular keyword values for the transition-timing-function property include linear, ease-in, ease-out, and ease-in-out.







### Transition Delay:
#### On top of declaring the transition property, duration, and timing function, you can also set a delay with the transition-delay property. 
#### The delay sets a time value, seconds or milliseconds, that determines how long a transition should be stalled before executing. As with all other transition properties, to delay numerous transitions, each delay can be declared as comma separated values.





### Shorthand Transitions (#shorthand-transitions):
#### Declaring every transition property individually can become quite intensive, especially with vendor prefixes. 
#### Fortunately there is a shorthand property, transition, capable of supporting all of these different properties and values. Using the transition value alone, you can set every transition value in the order of transition-property, transition-duration, transition-timing-function, and lastly transition-delay.






### Animations (#animations):
#### Transitions do a great job of building out visual interactions from one state to another, and are perfect for these kinds of single state changes.
#### However, when more control is required, transitions need to have multiple states. In return, this is where animations pick up where transitions leave off.





### Animations Keyframes:
#### To set multiple points at which an element should undergo a transition, use the @keyframes rule.
#### The @keyframes rule includes the animation name, any animation breakpoints, and the properties intended to be animated. 





### Animation Name:
#### Once the keyframes for an animation have been declared they need to be assigned to an element.
#### o do so, the animation-name property is used with the animation name, identified from the @keyframes rule, as the property value. The animation-name declaration is applied to the element in which the animation is to be applied to.






### Animation Duration, Timing Function, & Delay:
#### Once you have declared the animation-name property on an element, animations behave similarly to transitions. 
#### They include a duration, timing function, and delay if desired. To start, animations need a duration declared using the animation-duration property. As with transitions, the duration may be set in seconds or milliseconds.






### Customizing Animations (#customizing-animations):
#### Animations also provide the ability to further customize an element’s behavior, including the ability to declare the number of times an animation runs, as well as the direction in which an animation completes.




### Animation Iteration:
#### By default, animations run their cycle once from beginning to end and then stop.
#### To have an animation repeat itself numerous times the animation-iteration-count property may be used. Values for the animation-iteration-count property include either an integer or the infinite keyword. Using an integer will repeat the animation as many times as specified, while the infinite keyword will repeat the animation indefinitely in a never ending fashion.


### Animation Direction:
#### On top of being able to set the number of times an animation repeats, you may also declare the direction an animation completes using the animation-direction property. Values for the animation-direction property include normal, reverse, alternate, and alternate-reverse.
#### The normal value plays an animation as intended from beginning to end. The reverse value will play the animation exactly opposite as identified within the @keyframes rule, thus starting at 100% and working backwards to 0%.




### Animation Play State:
#### he animation-play-state property allows an animation to be played or paused using the running and paused keyword values respectively.
#### When you play a paused animation, it will resume running from its current state rather than starting from the very beginning again.





### Animation Fill Mode:
#### The animation-fill-mode property identifies how an element should be styled either before, after, or before and after an animation is run.
#### The animation-fill-mode property accepts four keyword values, including none, forwards, backwards, and both.
#### The none value will not apply any styles to an element before or after an animation has been run
#### The forwards value will keep the styles declared within the last specified keyframe. These styles may, however, be affected by the animation-direction and animation-iteration-count property values, changing exactly where an animation ends.
#### The backwards value will apply the styles within the first specified keyframe as soon as being identified, before the animation has been run. This does include applying those styles during any time that may be set within an animation delay. The backwards value may also be affected by the animation-direction property value.




### Shorthand Animations (#shorthand-animations):
#### Fortunately animations, just like transitions, can be written out in a shorthand format.
#### This is accomplished with one animation property, rather than multiple declarations. The order of values within the animation property should be animation-name, animation-duration, animation-timing-function, animation-delay, animation-iteration-count, animation-direction, animation-fill-mode, and lastly animation-play-state.

