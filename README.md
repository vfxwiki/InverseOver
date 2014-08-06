InverseOver
===========

This is an alternative way of using a matte generated from a key that retains fine detail that an normal over node on its own cannot do. It generates a thin key for the translucent detail on motion blur, hair, dirt on glass etc. I will require a normal key for its core.

This process is able to retain detail in the same way as various image blending techniques  i.e. blending through back grounds with soft eroded keys onto the despill plate, Additive Keying, Keymix. But this is not an image blending technique and so can be used when a matte is required i.e. for stereo conversion. Another advantage of this technique is that it blends changes of luminace in a background very naturally i.e. flashes/explosions with smoke.

The central idea to this is that the matte from a key loses detail when the bg is scaled to black (and the FG to white). This technique allows one to use an unscaled matte. 

The weakness of this technique is that it works with the keying stratagy of having the best cleaned up plate to start with and so teribly lit screens will need to be leveled first.

INSTRUCTIONS:
1: Create a clean plate

2: Generate a simple matte with as little manipulation to it as possible, it sposed to be thing i.e. the has greys instead of blacks. What works well for the plate differs he are some of the options:
a) a colour channel difference 'ala steve wright'
b) a one colour-pick primatte
c) keylight set to a single RGB colour and not scalled i.e. for a greenscreen R:0/G:1/B:0

3: Do a despill, and as with any normal despil plate for keying change the luminace of the screen values to be similar to the BG plate

4: Plug in all in. Select a crop area of the screen and set the frame. This selects a flat averaged solid greenscreen colour as well as a flat averaged solid matte that is used in the inverseOver node

5: Use the 'setup' drop down to go into 'keyDensity' and pull the slider untill the bars match/disapear.

6: Do the same for 'fixMatteBlacks' slider, but in this case if red warning areas appear, back off till the red is no longer there.

7: switch the set up mode off

EXPLANATION:
The InverseOverKeyer outputs two channels, RGBA(A being the key) and InverseOver(RGBA - RGB is the selected solid colour and A is the selected solid grey from the key)

The InverseOver Channel is used with the InverseOver node. It adjusts every pixel of the BG equally to compensate for the process of doing an over with a matte that is too thin. To explain... if you used a key with greys rather than blacks as its darkest value it would make your backgound take on the colour of the screen, this would be a problem, but not if you compensated for this by doing an inverse of an over to the background before the over.


CREDIT:
Credit for this node goes to Thomas Dyn where i first came accros the idea, since then another CTD has shown me a very similar idea from his old ILM toolbox, but the implementation of using bars to match the densities i have not seen anywhere else. 

LICENCE:
licence
===========
By downloading or copy and pasting a file from this repository you agree to the general license terms below.
Copyright (c) 2010 till present
All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:
Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
Neither the name of Nukepedia nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.
THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS 'AS IS' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOO/ OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
