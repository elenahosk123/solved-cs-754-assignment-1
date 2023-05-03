Download Link: https://assignmentchef.com/product/solved-cs-754-assignment-1
<br>
Advanced Image Processing




<ol>

 <li>Let θ<strong><sup>*</sup></strong> be the result of the following minimization problem (BP): min~θ I1 such that y −4)Ψθ 12 ≤ ε, where y is an m-element measurement vector, 4) is a m×n measurement matrix (m &lt; n), Ψ is a n×n orthonormal basis in which n-element signal x has a sparse representation of the form x = Ψθ. Notice that y = 4)x + η and ε is an upper bound on the magnitude of the noise vector η.</li>

</ol>

Theorem 3 we studied in class states the following: If 4) obeys the restricted isometry property with isometry constant 2s &lt; √2 − 1, then we have 1θ − θ<strong><sup>*</sup></strong>12 ≤ C1s−<sup>1</sup>/<sup>2</sup> 1θ − θ<strong>s</strong>11 + C2ε where C1 and C2 are functions of only<sub> 2</sub><sub>s</sub> and where ∀i ∈ S, θ<strong>s</strong>i = Oi; ∀i ∈/ S, θ<strong>s</strong>i = 0. Here S is a set containing the s largest magnitude elements of θ.

A curious student asks the following questions: ‘(1) It appears that the upper bound on Iθ−θ<strong><sup>*</sup></strong> 12 is reduced as s increases, which goes against the very premise of compressed sensing. How do we address this apparent discrepancy? (2) It also appears that the error bound is independent of m. How do you address this? (3) Now consider that I gave you another theorem (called Theorem 3A), which is the same as Theorem 3 except that it requires that 2s &lt; 0.3. Out of Theorem 3 and Theorem 3A, which is the more useful theorem? Why? (4) It appears that if I set ε = 0 in BP, I can always reduce the upper bound on the error even if the noise vector η has non-zero magnitude. What am I missing?’

Your job is to answer all four of the student’s questions. [5+5+5+5=20 points]

<ol start="2">

 <li>In class, we studied a video compressive sensing architecture from the paper ‘Video from a single expo­sure coded snapshot’ published in ICCV 2011 (See <a href="http://www.cs.columbia.edu/CAVE/projects/single_">http://www.cs.columbia.edu/CAVE/projects/single_</a> shot_video/). Such a video camera acquires a ‘coded snapshot’ E<sub>u</sub> in a single exposure time interval u. This coded snapshot is the superposition of the form E<sub>u</sub> = &gt;T t=1 Ct Ft where Ft is the image of the scene at instant t within the interval u and Ct is a randomly generated binary code at that time instant, which modulates Ft. Note that E<sub>u</sub>, Ft and Ct are all 2D arrays. Also, the binary code generation as well as the final summation all occur within the hardware of the camera. Your task here is as follows:</li>

</ol>

<ul>

 <li>Read the ‘cars’ video in the homework folder in MATLAB using the ‘mmread’ function which has been provided in the homework folder and convert it to grayscale. Extract the first T = 3 frames of the</li>

 <li>Generate a H × W × T random code pattern whose elements lie in {0, 1}. Compute a coded snapshot using the formula mentioned and add zero mean Gaussian random noise of standard deviation 2 to it. Display the coded snapshot in your report.</li>

</ul>




<ul>

 <li>Given the coded snapshot and assuming full knowledge of Ct for all t from 1 to T, your task is to estimate the original video sequence Ft. For this you should rewrite the aforementioned equation in the form Ax = b where x is an unknown vector (vectorized form of the video sequence). Mention clearly what A and b are, in your report.</li>

 <li>You should perform the reconstruction using Orthogonal Matching Pursuit (OMP). For computational efficiency, we will do this reconstruction patchwise. Write an equation of the form Ax = b where x represents the i<sup>th</sup> patch from the video and having size (say) 8 × 8 × T and mention in your report what A and b stand for. For perform the reconstruction, assume that each 8 × 8 slice in the patch is sparse or compressible in the 2D-DCT basis. Carefully work out the error term in the OMP algorithm, and explain this in your report!</li>

 <li>Repeat the reconstruction for all overlapping patches and average across the overlapping pixels to yield the final reconstruction. Display the reconstruction and mention the relative mean squared error between reconstructed and original data, in your report as well as in the code.</li>

 <li>Repeat this exercise for T = 5, T = 7 and mention the mention the relative mean squared error between reconstructed and original data again.</li>

 <li>Note: To save time, extract a portion of about 120 × 240 around the lowermost car in the cars video and work entirely with it. In fact, you can show all your results just on this Some sample results are included in the homework folder.</li>

 <li>Repeat the experiment with any consecutive 5 frames of the ‘flame’ video from the homework folder. [35 points = 18 points for successful OMP implementation + 7 points for carefully presenting error term bound + 10 points for displaying of all results]</li>

</ul>

<ol start="3">

 <li>We will prove why the value of the coherence between m×n measurement matrix 4 (with all rows normalized to unit magnitude) and n×n orthonormal representation matrix ‘ must lie within the range (1, √n). Recall that the coherence is given by the formula p(4, ‘) = √nmaxi,j∈{0,1,…,n−1}|<sup>4</sup><strong><sup>i</sup></strong><sup>t</sup> ‘<strong>j</strong>|. Proving the upper bound should be very easy for you. To prove the lower bound, proceed as follows. Consider a unit vector g ∈ R<sup>n</sup>. We know that it can be expressed as g = ~nk=1 αk ‘<strong>k </strong>as ‘ is an orthonormal basis. Now prove that</li>

</ol>

<u>|α</u><u>i</u><u>|</u> . Exploiting the fact that g is a unit vector, prove that the minimal p(g, ‘) = √nmaxi∈{0,1,…,n−1} <u>~</u><u>n</u> j=1 α2 j / 1/n ~n

value of coherence is attained when g =              k=1 ‘<strong>k </strong>and that hence the minimal value of coherence is

<ol>

 <li>[10 points]</li>

 <li>Compressive sensing reconstructions involve estimating a sparse signal x ∈ R<sup>n</sup>, n &gt;&gt; 2 from a vector y ∈ R<sup>m</sup>(m &lt;&lt; n) of compressed measurements of the form y = 4x where 4 ∈ R<sup>m×n</sup> is the measurement matrix (assume there is no noise). Now answer the following questions, from first principles. Do not merely quote theorems or algorithms.</li>

</ol>

<ul>

 <li>If x has only 1 non-zero element and the other elements are zero, can you uniquely estimate x if m = 1? If yes, how? If not, why not? Now further suppose, you knew beforehand the index (but not the value) of the non-zero element of x? Does this help you any further? If yes, how? If not, why not?</li>

 <li>If x has only 1 non-zero element and the other elements are zero, can you uniquely estimate x if m = 2? If yes, how? If not, why not?</li>

 <li>If x has only 2 non-zero elements and the other elements are zero, can you uniquely estimate x if m = 3? If yes, describe an algorithm that is guaranteed to estimate it accurately. If not, explain why not, and explain whether there are any special instances of 4 for which unique estimation is possible?</li>

 <li>Repeat part (c) with m = 4. [1+2+3+4=10 points]</li>

</ul>

<ol start="5">

 <li>Read the paper ‘Coded aperture compressive temporal imaging’ which is a type of video compressive sensing camera developed at Duke University. The paper can be accessed here: https://www.osapublishing.org/ oe/fulltext.cfm?uri=oe-21-9-10526&amp;id=253002. A local copy is also placed in the homework folder. Answer the following questions:</li>

</ol>




<ul>

 <li>Explain the similarities and differences between this architecture and the video compressed sensing architecture using coded snapshots (Hitomi et al, ICCV 2011) that we studied in class.</li>

 <li>What cost function is the reconstruction algorithm in the paper based on? Explain the meaning and dimensions of every term in the cost function. (Note: you are not expected to describe the algorithms that minimize this cost function, but only mention the cost function itself) [8+7=15 points]</li>

</ul>

<ol start="6">

 <li>Here is our mandatory Google search question. Note that this is the only question for which you can perform a google search to get the answer. A very interesting application of compressed sensing is in the area of optical or electron microscopy. Your task is to search for a research paper which applies compressed sensing in this application. Answer the following questions briefly:</li>

</ol>

<ul>

 <li>Mention the title of the paper, where and when it was published and include a link to it.</li>

 <li>Very briefly describe the hardware architecture used in the paper. You may refer to figures from the paper itself.</li>

 <li>What reconstruction techhnique or cost function does the paper adopt for the sake of compressive reconstruction in this application? [3+4+4=10 points]</li>

</ul>