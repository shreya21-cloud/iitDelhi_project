Grasp-CLIP: Pick Up What You Want - Notes
1. Problem Statement

Traditional robot grasping systems can generate grasp poses for objects, but they cannot easily understand commands like:

"Pick up the apple"

Challenges:

Cannot identify specific target objects from text instructions.
Slow inference speed.
High model complexity.
Low grasp precision in cluttered scenes.

Goal:

Enable robots to grasp a specific object using natural language commands.
Improve speed, precision, and generalization.

2. Main Idea of Grasp-CLIP

Grasp-CLIP combines:

GSNet (6-DoF grasp generation)
CLIP (Image + Text understanding)

Input Modalities:

Point Cloud
RGB Image
Text Instruction

Example:

Text:

Pick up the red bell pepper

Output: Only grasp poses belonging to the red bell pepper.


3. What is GSNet?
GSNet is the base grasping network.

Functions:
Takes point cloud as input.
Generates 1024 candidate grasp points.
Predicts:
Approach direction
Grasp rotation
Grasp depth
Gripper width
Grasp score

Limitation:

Does not know which object is the target object.

4. Why CLIP is Used?

CLIP learns relationships between:

Images
Text

Benefits:

Understands object names.
Understands attributes like:
Color
Shape
Size
Helps generalize to unseen objects.

Example:Training:

Green Bell Pepper

Testing:

Yellow Bell Pepper

CLIP can still understand the relationship.
