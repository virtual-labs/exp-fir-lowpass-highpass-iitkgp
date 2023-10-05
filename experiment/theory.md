## Introduction

**About the Experiment**


This experiment enables a student to learn

- How to realize functionality of a 3-to-8 line active low Decoder viz. 74138 IC. That is on setting the two active low and one active high enable inputs to proper level, one can verify that one and only one of the eight active low outputs is asserted based on the values assigned to three select input.
- How to cascade two 74138 IC's to implement a 4-to-6 active low decoder.


## Theory

#### Part1
                        
IC 74138 works as a 3-to-8 active low decoder,based on the values assigned to three select inputs of the three enable inputs, G1 must be made high value while <font style="text-decoration:overline">G</font>2A and <font style="text-decoration:overline">G</font>2B must be low. The eight active low inputs (<font style="text-decoration:overline">Y</font>0 to <font style="text-decoration:overline">Y</font>7) correspond to eight maxterms (M0 to M7) or in other words, component of the corresponding minterms m0-m7. For example, <font style="text-decoration:overline">Y0</font> = component of <font style="text-decoration:overline">C</font>&nbsp;<font style="text-decoration:overline">B</font>&nbsp;<font style="text-decoration:overline">A</font> = C+B+A. <br />
                            <div align="center">
                            <img src="images/74138.jpg" style="width:500px;height:400px;" /> 
                            <br />
                            Figure 1 (IC 74138)</div>
 

 
 $$ \\overline { G2A } $$ |$$ \\overline { G2B } $$ | G1  |  C |  B |  A | $$ \\overline{ Y0 } $$  | $$ \\overline{ Y1 } $$   | $$ \\overline{ Y2 } $$   | $$ \\overline{ Y3 } $$  | $$ \\overline{ Y4 } $$  | $$ \\overline{ Y5 } $$  | $$ \\overline{ Y6 } $$  |$$ \\overline{ Y7 }$$ |
:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|:--|
 L | L  |H|0|0|0|0|1|1|1|1|1|1|1|
 L | L  |H|0|0|1|1|0|1|1|1|1|1|1|
 L | L  |H|0|1|0|1|1|0|1|1|1|1|1|
 L | L  |H|0|1|1|1|1|1|0|1|1|1|1|
 L | L  |H|1|0|0|1|1|1|1|0|1|1|1|
 L | L  |H|1|0|1|1|1|1|1|1|0|1|1|
 L | L  |H|1|1|0|1|1|1|1|1|1|0|1|
 L | L  |H|1|1|1|1|1|1|1|1|1|1|0|

Figure 2 Truth table for 3 to 8 decoder
                            
                             
  #### Part2
                             
 Cascading two 74138 IC(Two 3 to 8 active low decoder) we can achieve a 4 to 16 active low decoder.
                              
  <font style="text-decoration:overline">G2A</font> and <font style="text-decoration:overline">G2B</font> inputs of the first IC(74138) and G1 input of 2nd IC(74138) are shorted and it acts as MSB of 4 binary select input .
                              <font style="text-decoration:overline">G2A</font> &amp;<font style="text-decoration:overline">G2B</font> of second IC(74138) is kept low.G1 of 1st IC is kept always high.</p>
                           

                             
 <img src="images/dual-74138.JPG" style="width:700px;height:600px;"/> 
                             
<p>Figure 3: 4 to 16 decoder  cascadeding two 3 to 8 decoder
                             </p>
                          <table width="80%"  border="0" cellspacing="1px" cellpadding="2" bgcolor="#999999">
                             
<tr bgcolor="#FFFFCC">
                             <td colspan="4" width="30%">Select Inputs</font></td>
                             <td colspan="8">1st Decoder</font></td>
                             <td colspan="8">2nd Decoder</font></td>
                             </tr>
                             <tr bgcolor="#FFFFCC">
                             <td width="20%">D</td>
                             <td width="20%">C</td>
                             <td width="20%">B</td>
                             <td width="20%">A</td>
                             <td><font style="text-decoration:overline">Y0</font></td>
                             <td><font style="text-decoration:overline">Y1</font></td>
                             <td><font style="text-decoration:overline">Y2</font></td>
                             <td><font style="text-decoration:overline">Y3</font></td>
                             <td><font style="text-decoration:overline">Y4</font></td>
                             <td><font style="text-decoration:overline">Y5</font></td>
                             <td><font style="text-decoration:overline">Y6</font></td>
                             <td><font style="text-decoration:overline">Y7</font></td>
                             <td><font style="text-decoration:overline">Y0</font></td>
                             <td><font style="text-decoration:overline">Y1</font></td>
                             <td><font style="text-decoration:overline">Y2</font></td>
                             <td><font style="text-decoration:overline">Y3</font></td>
                             <td><font style="text-decoration:overline">Y4</font></td>
                             <td><font style="text-decoration:overline">Y5</font></td>
                             <td><font style="text-decoration:overline">Y6</font></td>
                             <td><font style="text-decoration:overline">Y7</font></td>
                             
                            
  </tr>
                                
                                
 <tr bgcolor="#FFFFCC">
                             <td >0</td>
                             <td>0</td>
                             <td >0</td>
                             <td>0</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
 </tr>
                             
                             
 <tr bgcolor="#FFFFCC">
                             <td>0</td>
                             <td >0</td>
                             <td >0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
 </tr>
                             
                             
 <tr bgcolor="#FFFFCC">
                             <td>0</td>
                             <td >0</td>
                             <td >1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
                             
 </tr>
                             
<tr bgcolor="#FFFFCC">
                             <td>0</td>
                             <td >0</td>
                             <td >1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
                             
  </tr>
                             
 <tr bgcolor="#FFFFCC">
                             <td>0</td>
                             <td >1</td>
                             <td >0</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
                             
 </tr>
                             
                             
<tr bgcolor="#FFFFCC">
                             <td>0</td>
                             <td >1</td>
                             <td >0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
                             
 </tr>
                             
                             
 <tr bgcolor="#FFFFCC">
                             <td>0</td>
                             <td >1</td>
                             <td >1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
                             
 </tr>
                             
<tr bgcolor="#FFFFCC">
                             <td>0</td>
                             <td >1</td>
                             <td >1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
                             
</tr>
                             
                             
                             
                             
                             
 <tr bgcolor="#FFFFCC">
                             <td>1</td>
                             <td >0</td>
                             <td >0</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
 </tr>
                             
                             
                             
                             
 <tr bgcolor="#FFFFCC">
                             <td>1</td>
                             <td >0</td>
                             <td >0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
                             
</tr>
                             
                             
 <tr bgcolor="#FFFFCC">
                             <td>1</td>
                             <td >0</td>
                             <td >1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
                             
  </tr>
                             
                             
 <tr bgcolor="#FFFFCC">
                             <td>1</td>
                             <td >0</td>
                             <td >1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
                             
 </tr>
                             
                             
                             
<tr bgcolor="#FFFFCC">
                             <td>1</td>
                             <td >1</td>
                             <td >0</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             
                             
 </tr>
                             
                             
                             
<tr bgcolor="#FFFFCC">
                             <td>1</td>
                             <td >1</td>
                             <td >0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             
</tr>
                             
                             
 <tr bgcolor="#FFFFCC">
                             <td>1</td>
                             <td >1</td>
                             <td >1</td>
                             <td>0</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             <td>1</td>
                             
                             
 </tr>
                             
                             
  <tr bgcolor="#FFFFCC">
                             <td>1</td>
                             <td >1</td>
                             <td >1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>1</td>
                             <td>0</td>
                             
                             
 </tr>
                             
                             
                             
                             
                             
 </table>
                             
 <br />
                              <p>Figure 4&nbsp;: Truth table for 4 to 16 decoder</p>
                              
                              
                              
                             
                             
#### Part 3

A decoder with active high outputs generates minterms. Whereas, a decoder with active low outputs generates maxterms (i.e.  complements of
the corresponding minterm).
Thus, if a function is specified as a sum of minterms or equivalently as a product of maxterms, 
it can be realized by a decoder with active low outputs and additional AND/NAND gates. 


For example, consider the following
<br />

F1 (A,B,C) = &Sigma; m (1,2)
<br />

F2 (A,B,C) = &Sigma; m (0,1,2,3,4,5)

<br />

<div align="center">

<img src="images/decoder-syn.JPG" style="width:400px;height:300px;"/>
     
</div>                           


 <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3.2.2/es5/tex-mml-chtml.js"></script>    
 