Introduction:

PhotoreceptorOrientation is a set of Matlab programs for measuring photoreceptor orientations relative to the approximate center of the mouse eye. 
The programs require high resolution images of cross-sections from fixed mouse eyes.

Instructions for analyzing example images:

Prepare eye image for measuring photoreceptor orientations:
1) 	Download and extract PhotoreceptorOrientation folder from GitHub at: 
2) 	Download example images from the Open Science Framework at: https://osf.io/4kuzj/
2) 	Open PhotoreceptorOrientation_Eye.m in Matlab.
3) 	Enter Identifiers on Lines 20-26.
		%% Enter identifiers
		Genotype ='C57BL6J'; % Enter details about rearing, genotype, and age
		LDcycle ='Dark-reared'; % Enter location where mouse was housed
		Eye ='Eye1'; % Enter label for eye
		rotationangle = 90; % Rotate eye to point towards lower right corner for consistency across images
		value = (pi/6); % Approximate angle of the retina beyond pi
		threshold = 150; % Set threshold intensity above which pixels become 1 and below which, pixels become 0.  May need to try a few different values after seeing pixel intensity histrogram.
		filename = 'Dark-reared.tif'; % Enter filename of the image and include file path if image is not in same folder as PhotoreceptorOrientation_EYE.m
4) 	Run program and follow prompts.
5) 	Crop image by drawing rectangle near the eye's perimeter. Double click within the drawn rectangle.
6) 	The program will find the approximate center of the eye using the regionprops('Centroid') function.
7) 	Identify the approximate pupil center by drawing a line from one end of the iris to the other. 
		Then, drag the line to the anterior surface of the lens and single click.	
8) 	Divide the retina into 7 retinal sectors by drawing a line from the eye's center point 'C' to the right-most edge of the retina.
9) 	The program will save the workspace and the processed image for further analysis using PhotoreceptorOrientation_MeasureOuterSegmentAngles_First and _Second.

NOTE: See PhotoreceptorOrientation_Eye_Example.pdf for example figures.

Measure outer segment angles:

10) 	Open and Run PhotoreceptorOrientation_GenerateOuterSegmentTable.m to generate table for storing outer segment angle measurements.
11)	Open PhotoreceptorOrientation_MeasureOuterSegmentAngles_First.m to measure first set of outer segment angles in retinal sector -3.
		Check identifiers and enter RetinalRegion = -3 on Line 12 and then Run the program.
12)	Use the zoom function in the figure to focus on rods in the left-most sector of the retina.
13)	Identify 3 rod outer segments that are clearly resolved in the image. Single-click on the outer-segment tip of each of the 3 identified rods.
14)	Single-click on the outer segment base of each of the 3 identified rods (in the same sequence as in "13)").
15) 	The program will automatically draw a line from the outer segment tip to the outer segment base 
		and another automatic line from the outer segment tip to the eye's center point 'C'.
16)	The program will measure the angle using the dot product of these two automatic lines and record the values in a table.
17)	Open PhotoreceptorOrientation_MeasureOuterSegmentAngles_Second.m to measure outer segment angles in retinal sector -2.
		Check identifiers and enter RetinalRegion = -2 on Line 12 and then Run the program.
18) 	Use the drag function in the figure to move to the next retinal sector (-2).
19)	Repeat "13)" to "16)" to measure outer segment angles in retinal sector -2.
20)	Repeat "17)" to "19)" to measure outer segment angles in each remaining retinal sector.

NOTE: 	See PhotoreceptorOrientation_MeasureOuterSegmentAngles_Example.pdf for example figures.

Measure inner segment angles:

21)	Open and Run PhotoreceptorOrientation_GenerateInnerSegmentTable.m to generate table for storing inner segment angle measurements.
22)	Open PhotoreceptorOrientation_MeasureInnerSegmentAngles_First.m to measure first set of inner segment angles in retinal sector -3.
		Check identifiers and enter RetinalRegion = -3 on Line 12 and then Run the program.
23) 	The program will automatically open the eye image with outer segements identified from "15)".
24) 	Single-click on the distal inner segment tip of a clearly-resolved inner segment. 
		Note: It is not always possible to see a clearly-defined inner segment connected to the identified outer segments.
		In this case, identify any clearly-defined inner segment within the same field-of-view.
25)	Single-click on the inner segment base of each of the 3 identified rods (in the same sequence as in "24)").
26) 	The program will automatically draw a line from the inner segment tip to the inner segment base 
		and another automatic line from the inner segment tip to the eye's center point 'C'.
27)	The program will measure the angle using the dot product of these two automatic lines and record the values in a table.
28)	Open PhotoreceptorOrientation_MeasureInnerSegmentAngles_Second.m to measure second set of inner segment angles in retinal sector -2.
		Check identifiers and enter RetinalRegion = -2 on Line 12 and then Run the program.
29) 	Repeat "24)" to "27)" to measure inner segment angles in retinal sector -2.
30) 	Repeat "28)" to "29)" to measure inner segment angles in each remaining retinal sector.

NOTE: 	See PhotoreceptorOrientation_MeasureInnerSegmentAngles_Example.pdf for example figures.

Plot measured outer segment angles and inner segment angles:

31) 	Open and Run PhotoreceptorOrientation_PlotMeasuredAngles.m to plot the mean +/- SD of outer segment angles (Top) and inner segment angles (Bottom).
		The plot shows the mean and SD values from identifed rods in a single eye.

NOTE:	See PhotoreceptorOrientation_PlotMeasuredAngles_Example.pdf for example figures.

Troubleshooting:

Please send any questions about troubleshooting to Daniel Silverman (dsilve33@alumni.jh.edu)
