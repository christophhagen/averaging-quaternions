# (Correctly) averaging quaternions
Python function for correct averaging of multiple quaternions. Quaternions representations provide no trivial means of averaging multiple quaternions. Even though avaraging of the components can be used in some cases, this approach has major drawbacks (as explained in the paper cited below).

The function given here implements are more mathematically correct way of averaging. The paper also provides a way to do a weighted average, but htis function is not implemented here (yet?).

## In principle based on:

Markley, F. Landis, Yang Cheng, John Lucas Crassidis, and Yaakov Oshman.
"Averaging quaternions." Journal of Guidance, Control, and Dynamics 30,
no. 4 (2007): 1193-1197.
Link: https://ntrs.nasa.gov/archive/nasa/casi.ntrs.nasa.gov/20070017872.pdf

## Code based on:

Tolga Birdal. "averaging_quaternions" Matlab code.
Linkhttp://jp.mathworks.com/matlabcentral/fileexchange/40098-tolgabirdal-averaging-quaternions

## Note on efficiency

This method is computationally expensive compared to naive mean averaging.
If only low accuracy is required (or the quaternions have similar orientations),
then quaternion averaging can possibly be done through simply averaging the
components.

### Comparison between different methods of averaging:

Claus Gramkow. "On Averaging Rotations"
Journal of Mathematical Imaging and Vision 15: 7–16, 2001, Kluwer Academic Publishers.
https://pdfs.semanticscholar.org/ebef/1acdcc428e3ccada1a047f11f02895be148d.pdf

### Side note
In computer graphics, averaging or blending of two quaternions is often done through
spherical linear interploation (slerp). Even though it's often used it might not be the best
way to do things, as described in this post:

Jonathan Blow.
"Understanding Slerp, Then Not Using It", February 2004
http://number-none.com/product/Understanding%20Slerp,%20Then%20Not%20Using%20It/
