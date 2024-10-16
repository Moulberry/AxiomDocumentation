## Modify

The Modify tool is designed for manipulating [selections](/tools/selection/intro.md) in various ways.

## Overview

| Mode             | Description                                                     |
| ---------------- | --------------------------------------------------------------- |
| Revolve          | Stretches the selection in a circular structure                 |
| Translate Copies | Clones the selection a set number of times with a custom offset |
| Rotate Copies    | A mix between Revolve and Translate Copies                      |
| Twist            | Twists a selection using an angle and axis                      |

## Revolve

With your selection active, two circular lines will appear, the red indicates the inner part of the revolve and the green indicates the exterior. The two lines pointing from the cursor position indicate the points where the rotation may start.

The Revolve tool can rotate on all three axes separately and has an option to control the amount of angle the tool uses. An angle of 360 does a full loop and 180 does a half loop.  

The **Add Translation** button will allow you to offset the end position of the revolve using whole or decimal numbers.

## Translate Copies

Similar to[stack](/builder/buildertools/stack.md), Translate Copies allows for offsetting by relative or absolute values. The count controls the amount of copies to be made with the offset. 

Relative offsets are multiplied by the size of the selection.

Absolute offsets are not multiplied so they are therefore absolute coordinates.  

## Rotate Copies

Like a mix between Revolve and Translate Copies, Rotate Copies rotates a set number of copies around a point set by the cursor. However, changing the **Type** from **Equidistant** to **Custom Angle** will remove the point rotation and rotate based on the set angle offset.

The **Add Translation** Toggle enables the ability to offset the end copy. An offset of 1 on the Y-axis will create a spiral shape.

## Twist

The Twist function twists a selection at an angle alongside an axis. 

The axis controls the face direction of the twist and the angle determines how much it should twist. 
