
## Theory
                        
<p>Finite Impulse Response (FIR) Filter</p>
<p  class="heading-content">FIR filters are digital filters with finite impulse response. They are also known as non-recursive digital filters as 
they do not have the feedback (a recursive part of a filter), even though recursive algorithms can be used for FIR filter 
realization. Hence it is an all zero filter. Therefore input and output difference equation for FIR filter is given by</p>

$$y(n)=b_0x(n)+b_1x(n-1)+b_2x(n-2)+...+b_(M-1)x(n-N+1)$$

<p  class="heading-content">Where b0, b1, b2 ... b(M-1) are filter coefficients. FIR filters are particularly useful for applications where exact 
linear phase response is required. The FIR filter is generally implemented in a non-recursive way which guarantees a 
stable filter.</p>
<p  class="heading-content">FIR filters can be designed using different methods, but most of them are based on ideal filter approximation. The 
objective is not to achieve ideal characteristics, as it is impossible anyway, but to achieve sufficiently good 
characteristics of a filter. The transfer function of FIR filter approaches the ideal as the filter order increases, 
thus increasing the complexity and amount of time needed for processing input samples of a signal being filtered.</p>
<center><img style="width:331px;height:239px;" src="images/pic-8.png" alt="" /><br/>
 Fig-1 </center>
<p  class="heading-content">FIR filters can have linear phase characteristic, which is not like IIR filters. Obviously, in such cases when it is 
necessary to have a linear phase characteristic, FIR filters are the only option available. If the linear phase 
characteristic is not necessary, as is the case with processing speech signals, FIR filters are not good solution at all.</p>
<p  class="heading-content">One of the drawbacks of FIR filters is a high order of designed filter. The order of FIR filter is remarkably higher 
compared to an IIR filter with the same frequency response. This is the reason why it is so important to use FIR filters 
only when the linear phase characteristic is very important.</p>
<p  class="heading-content">A number of delay lines contained in a filter, i.e. a number of input samples that should be saved 
for the purpose of 
computing the output sample, determines the order of a filter. For example, if the filter is assumed to be of order 10, 
it means that it is necessary to save 10 input samples preceding the current sample. All eleven samples will affect the 
output sample of FIR filter</p>
<p  class="heading-content">The transform function of a typical FIR filter can be expressed as a polynomial of a complex variable z^-1. All the poles 
of the transfer function are located at the origin. For this reason, FIR filters are guaranteed to be stable, whereas IIR 
filters have potential to become unstable</p>
<p>Basic concepts and FIR filter specification</p>
<p  class="heading-content">Most FIR filter design methods are based on ideal filter approximation. The resulting filter approximates the 
ideal characteristic as the filter order increases, thus making the filter and its implementation more complex</p>
<p  class="heading-content">First of all, it is necessary to learn the basic concepts that will be used further in this book. You should be aware 
that without being familiar with these concepts, it is not possible to understand analyses and synthesis of digital 
filters.</p>
<p>Figure 2.a and 2.b illustrates a low-pass digital filter specification. The word specification actually refers to the 
frequency response specification</p>
<center><img style="width:331px;height:224px;" src="images/pic-1.png" alt="" /><br/>
   Figure 2.a: Low-pass digital filter specification</center>
<center><img style="width:374px;height:228px;" src="images/pic-2.png" alt="" /><br/>
  Figure 2.b: Low-pass digital filter specification</center>

<p> &omega;<sub>p</sub> normalized cut-off frequency in the passband;</p>
<p> &omega;<sub>s</sub> normalized cut-off frequency in the stopband; </p>
<p>&delta;<sub>1</sub>maximum ripples in the passband</p>
<p>&delta;<sub>2</sub>minimum attenuation in the stopband [dB]</p>
<p>a<sub>p</sub> maximum ripples in the passband; and</p>
<p>a<sub>s</sub>minimum attenuation in the stopband [dB].
  
$$a_p=20log_{10}(\frac{1+\delta_1}{1-\delta_1})$$

$$a_s=-20log_{10}\delta_1$$

<p>Frequency normalization can be expressed as follows: </p>
<p><p style="text-align:center">`omega=(2pif/f_s)`</p>
<p>where:</p>
<p>f<sub>s</sub>is a sampling frequency;</p>  
<p>f is a frequency to normalize; and</p>
<p> &omega;<sub></sub> is normalized frequency.</p>
<p>Specifications for high-pass, band-pass and band-stop filters are defined almost the same way as those for low-pass filters.
Figure 3.a and 3.b illustrates a high-pass filter specification</p>

<center><img style="width:364px;height:245px;" src="images/pic-4.png" alt="" /><br/>

Figure 3.b: High-pass digital filter specification</center>

<center><img style="width:385px;height:235px;" src="images/pic-5.png" alt="" /><br/>

Figure 3.b: High-pass digital filter specification</center>

<p  class="heading-content">Comparing these two figures 2.a, 2.b and 3.a, 3.b, it is obvious that low-pass and high-pass filters have similar 
specifications. The same values are defined in both cases with the difference that in the later case the pass band is 
substituted by the stop band and vice versa.</p>
<p>Finite impulse response (FIR) filter design methods</p>
<p  class="heading-content">The filter design process starts with specifications and requirements of the desirable FIR filter. Which method is to be 
used in the filter design process depends on the filter specifications and implementation</p>
<p>There are essentially three well-known methods for FIR filter design namely:</p>
<p>1.The window method.</p>
<p>2.The frequency sampling technique.</p>
<p>3.Optimal filter design methods</p>
<p  class="heading-content">Each of the given methods has its advantages and disadvantages. Thus, it is very important to carefully choose the right
method for FIR filter design. Due to its simplicity and efficiency, the window method is most commonly used method for 
designing filters. The sampling frequency method is easy to use, but filters designed this way have small attenuation in 
the stop band.</p>
<p>Out of these three techniques we are going to discuss about window method only</p>
<p>Ideal filter approximation</p>
<p  class="heading-content">The ideal filter frequency response is used when designing FIR filters using window functions. The objective is to compute 
the ideal filter samples. FIR filters have finite impulse response, which means the ideal filter frequency sampling must 
be performed in a finite number of points. As the ideal filter frequency response is infinite, it is easy to produce 
sampling errors. The error is less as the filter order increases. Figure 4.a and 4.b illustrates the transfer functions of 
two standard ideal filters</p>

<center><img style="width:654px;height:295px;" src="images/pic-6.png" alt="" /><br/>

 Figure 4.a and 4.b: Transfer functions of two standard ideal filters </center>

<p>The ideal filter frequency response can be computed via inverse Fourier transform. The two standard ideal filters frequency
responses are contained in the table 1 below.</p>

<center><img style="width:502px;height:219px;" src="images/pic-7.png" alt="" /><br/>

   Table 1: The frequency responses of two standard ideal filters</center>

<p>The value of variable n ranges between 0 and N, where N is the filter order. A constant M can be expressed as M = N / 2. 
Equivalently, N can be expressed as N = 2M</p>
<p  class="heading-content">The constant M is an integer if the filter order N is even, which is not the case with odd order filters. If M is an 
integer (even filter order), the ideal filter frequency response is symmetric about its Mth sample which is found via 
expression shown in the table 1 above. If M is not an integer, the ideal filter frequency response is still symmetric, 
but not about some frequency response sample</p>
<p>Since the variable n ranges between 0 and N, the ideal filter frequency response has N+1 sample</p>
<p>If it is needed to find frequency response of a non-standard ideal filter, the expression for inverse Fourier transform 
must be used: </p><p style="text-align:center">`h_d[n]=1/pi int_(0)^(pi)e^(jomega(n-M))domega`</p>
<p>Non-standard filters are rarely used. However, if there is a need to use some of them, the integral above must be computed
via various numerical methods</p>
<p>FIR filter design using window functions</p>
<p>The FIR filter design process via window functions can be split into several steps:</p>
<p>1.Defining filter specifications;</p>
<p>2.Specifying a window function according to the filter specifications;</p>
<p>3.Computing the filter order required for a given set of specifications;</p>
<p>4.Computing the window function coefficients;</p>
<p>5.Computing the ideal filter coefficients according to the filter order;</p>
<p>6.Computing FIR filter coefficients according to the obtained window function and ideal filter coefficients</p>
<p  class="heading-content">7.If the resulting filter has too wide or too narrow transition region, it is necessary to change the filter order by 
increasing or decreasing it according to needs, and after that steps 4, 5 and 6 are iterated as many times as needed</p>
<p  class="heading-content">The final objective of defining filter specifications is to find the desired normalized frequencies , transition width and 
stopband attenuation. The window function and filter order are both specified according to these parameters. Accordingly,
the selected window function must satisfy the given specifications.</p>
<p  class="heading-content">After this step, that is, when the window function is known, we can compute the filter order required for a given set of 
specifications.</p>
<p  class="heading-content">When both the window function and filter order are known, it is possible to calculate the window function coefficients w[n]
using the formula for the specified window function</p>
<p  class="heading-content">After estimating the window function coefficients, it is necessary to find the ideal filter frequency samples. The final
objective of this step is to obtain the coefficients hd[n]. Two sequences w[n] and hd[n] have the same number of elements.</p>
<p>The next step is to compute the frequency response of designed filter h[n] using the following expression:</p><p style="text-align:center">`h[n]=w[n].h_d[n]`</p>
<p  class="heading-content">Lastly, the transfer function of designed filter will be found by transforming impulse response via Fourier 
transform:</p><p style="text-align:center">`H(e^(jomega))=sum_(n=0)^(N)h[n].e^(-jnomega)`</p>
<p  class="heading-content">If the transition region of designed filter is wider than needed, it is necessary to increase the filter order, 
reestimate the window function coefficients and ideal filter frequency samples, multiply them in order to obtain 
the frequency response of designed filter and reestimate the transfer function as well. If the transition region is 
narrower than needed, the filter order can be decreased for the purpose of optimizing hardware and/or software resources. 
It is also necessary to reestimate the filter frequency coefficients after that. For the sake of precise estimates, the filter order should be decreased or increased by 1.</p>
<p>Window functions</p>
<p>The window method is most commonly used method for designing FIR filters. The simplicity of design process makes this 
method very popular.</p>
<p  class="heading-content">A window is a finite array consisting of coefficients selected to satisfy the desirable requirements. This chapter provides 
a few methods for estimating coefficients and basic characteristics of the window itself as well as the result filters 
designed using these coefficients. The point is to find these coefficients denoted by w[n].</p>
<p>When designing digital FIR filters using window functions it is necessary to specify:</p>
<p>A window function to be used; and</p>
<p>The filter order according to the required specifications (selectivity and stop band attenuation).</p>
<p>These two requirements are interrelated. Each function is a kind of compromise between the two following requirements:</p>
<p>The higher the selectivity, i.e. the narrower the transition region; and</p>
<p>The higher suppression of undesirable spectrum, i.e. the higher the stop band attenuation.</p>
<p>Table 2 below contains all window functions mentioned in this chapter and briefly compares their selectivity and stop band 
attenuation</p>
<p>These two requirements are interrelated. Each function is a kind of compromise between the two following requirements:</p>
<p>The higher the selectivity, i.e. the narrower the transition region; and</p>
<p>The higher suppression of undesirable spectrum, i.e. the higher the stop band attenuation.</p>
<p>Table 2 below contains all window functions mentioned in this chapter and briefly compares their selectivity and stop band
attenuation.</p>
<p  class="heading-content">Special attention should be paid to the fact that minimum attenuation of window function and that of the filter designed 
using that function are different in most cases. The difference, i.e. additional attenuation occurs under the process of 
designing a filter using window functions. This affects the stop band attenuation to become additionally higher, which is 
very desirable.</p>
<p  class="heading-content">However, a drawback of this method is that the minimum stop band attenuation is fixed for each function. The following 
concepts such as the main lobe, main lobe width, side lobes, transition region, minimum stopband attenuation of window 
function and minimum stopband attenuation of designed filter are described in more detail in Figure 5</p>

<center><img style="width:691px;height:261px;" src="images/pic-9.png" alt="" /><br/>

Figure 5: Main lobe, main lobe width, side lobes, transition region</center>

<p  class="heading-content">As can be seen in the table 2 above, the stopband attenuation of these windows is not adjustable. It is only possible to
affect the transition region by increasing the filter order. For this reason it is preferable to start design process by 
specifying the appropriate window function on the basis of the stopband attenuation. It is most preferable to specify a 
window with the least stopband attenuation that satisfies the given requirements. This enables the designed filter to have 
the narrowest transition region</p>

<center><img style="width:662px;height:310px;" src="images/pic-10.png" alt="" /></center>

<p>Frequency Response and Weight Values of different windows types</p> 

<center><img style="width:667px;height:264px;" src="images/pic-11.png" alt="" /></center>

<p>This image is taken from "http://www.labbookpages.co.uk/audio/firwindowing.html"</p>


<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3.2.2/es5/tex-mml-chtml.js"></script>    
