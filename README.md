# FrontLimeAssembly
A peripheral companion board for the LimeSDR in the same formfactor. 

The barebones LimeSDR comes without any external filters or amplifiers. 
To actually use it for GSM/3G/LTE experiments one would really need some duplexers or at least channel filters.
A highly linear power amplifier with modest output would not be bad either. 

This project is a mostly generic board in the same form factor as LimeSDR. It can be stacked on top of it with risers and fed with 5V from USB or external PSU.
Or it can use the same cases as LimeSDR and the same cables. 

The aim is to provide at least the following features at as low cost as possible. 
-Cellular band duplexer in one of the more common cellular bands. eg. 850/900/1800/1900/2100. Preferably with generic layout so just changing the filter is enough. 
-Wideband reasonable quality LNA for increased sensitivity and overcoming the losses in filters. 
-Highly linear power amplifier to boost the output, while operating on the bands between 420-2500MHz.
-Generic pads for cheap SAW filters. Be it 433MHz, 868MHz or 2.4GHz.

The board is a 4 layer design with 1.6mm FR4. It is based on the original LimeSDR layout, just with significant modifications. 
This is done to ensure close mechanical compatibility with the LimeSDR board. 
In general it is hoped that re-using the mechanical layout and form factor will lead to wider availability of compatible cases and accessories. 


Rationale behind some of the component choices. 
Easy mode for the wideband LNA would be just using an MMIC like Mini-Circuits PSA-5043+ it is even conveniently specified for 0.05 to 4 GHz.
But LNA4ALL already exists and features that MMIC, along with few other boards with it. 
I wanted to design something that uses discrete parts while being cheap, wideband, stable and low noise. 
While this does sound hard to do I came across Infineon application note AN112 "Wideband LNA for 200 MHz to 6 GHz applications with BFR740L3RH".   
http://www.infineon.com/dgdl/AN112.pdf?fileId=db3a304314dca3890114f3d326f90671
But it uses a tiny transistor in a TSLP-3-9 package, which is only 1 x 0.6 x 0.4 mm in size. That and 0201 passives. 
Thankfully the concept is very forgiving so slightly larger design based on BFU730f and 0402/0603 passives is in the simulator. 

For the SAW filters and cellular band duplexer the parts choices are simple, use what ever case style that is both available in as many frequencies as possible and cheap on Mouser!
THankfully most SAW filters are now found in standard cases. 

For the PA/MPA I'm using AH1 from WatkinsJohnson/Triquint/Qorvo, because I have a bunch and the specs are good enough. 
For example SKY65162-70LF, MMG3014NT1 or MGA-30689 could be used as drop-in replacements.
The SOT-89 is very a common case so alternative parts should be available and easy to find. 

