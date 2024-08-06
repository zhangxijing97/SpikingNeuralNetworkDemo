# SpikingNeuralNetworksDemo

1. **Neuron**: The basic unit of the nervous system, responsible for processing and transmitting information.

2. **Synapse**: The junction between two neurons where information is transmitted from one neuron to another.

3. **Axon**: The long, thread-like part of a neuron that transmits impulses away from the cell body.

4. **Dendrite**: The branched projections of a neuron that receive signals from other neurons.

5. **Neuromorphic**: Referring to the design and development of hardware and software systems inspired by the structure and function of the human brain.

6. **Synaptic Plasticity**: The ability of synapses to strengthen or weaken over time, in response to increases or decreases in their activity.

7. **Neurotransmitter**: Chemicals that transmit signals across a synapse from one neuron to another.

# Slides Content

CosyneTutorial2022
SpikingNeuralNetworkModelsin 
Neuroscience
Dan Goodma n
ImperialCollegeLondon
ne ural
-
reckoning. org

Courseoutline
Part 1 
t
Class ical spiking neural networks

Biology/what is anSNN

Neuron models (LIF,HH)

Brieftour of neurondyna mics

Coincide nce detec tion
Exercises:

Improve on mysound localiser

Competition!
Part 2 
t
(Machine) learning with S NNs

Lea rning withSNNs

Mac hinelea rningand gradie nt desce nt

Surrogategradie ntdesce ntfor SNNs

Codingit in 
Py Torch

Asurprise
Exercise:

Impleme ntsound localisationwith 
surrogategradie ntdesce nt

^›Z]o}’}›ZÇ _
Practical
Aim:
after this course,youshould have an 
idea ofhow tostartusing SNNs
Not enoughtimetotalkabout ever y thing , 
so Iwillpoint tofurthe r resource s
Not muchtheor y.You can findthisin many 
good tex tbooksalrea dy.
Willtherefore missouta LOT.
Co mputation oriented
Brainuses SNNstocarr youtcomputations.
Alot of research focusses on propertie s of 
v˚µ„}v’vµıY
Aim:
how do those propertie s contributeto 
useful computations?
Useful canmea n for thebrain, and maybe  
alsofor machine lea rning (
maybe!
).

Sowhy should I careabout SNNs?
Ne uros cienc e.
SNNsare whatthe braindoes. Ifwe want 
tofullyunderstand thebrain we need to 
understandSNNs.
Intelligence .
˚Ç [„’Ç’ı
for gene ralintelligenc e.
Intellectual challenge.
Find awaytothinkabout hybr id 
continuous / discretesystem,and 
computationbased on this.
The com ingrevolution.
Excitingtimesfor SNNs withnew waysto 
trainthem(willtalkabout itin second half ).
Ne urom orphichardware.
Low power consumption.
Advantages ofcom putation with S NNs ?
 µoı]ÀPµ˚’’˚Y

Fastcomputation/ rapid dec ision
-
making

Multiplexing

Part 1 
t
 v˚µ„
networks

What is a spiking neural network?

Integrate
Lea k
Nonlinear, discontinuous dynamics!
A simple model: the leaky integrate
-
and
-
fire ( LIF) neuron
Mem brane potentialV evolves accordingtoa 
differential equation
ì

8

P

L

F
8
When a neuron rec eives a spike,Vincreases by 
syna pticweight w:
8
Z
8

E
S
When 
8

P
8
ç
 µ„^(]„’›]l˚_
resets:
8
Z
r

Howto simulate an LIF neuron?
ı [lo}}’}}ˆ˚

Slightly more complicated model: 2D LIF
Adddynam icthresho ld 
‡
ı
Threshold dyna mics:
ì
ç

8
ç

P

L
s

F
8
ç
New spikethreshold condition:
8

P
8
ç
After a spike:
8
Z
r
8
ç
Z
8
ç

E
Ü
8
ç
ISI (inter
-
sp ike inter val)

Hodgkin
-
Huxley and other biophysically detailed models
Cur rentsfrom manydifferent ioncha nnels
Eachhas an equation,add them together
Gives BIG equations,hard tounderstand
I prefer  touse reduc ed ( usually1dor 2d)LIF models
Der ive reduc ed models via various mathem aticalassumptions (e . g.slow/fast)
These act ually see mtofit thedatabetter !

Whistle stop tour into t he world of neuron dynamics
Bursting
Mechanisms
Many different type sand me cha nisms
Interact ionof slow and fast dynamic s
Possible roles
Relia bilityand signal tonoise ratio
Multiplexing
Bac k
-
propofer rorsignal (
Payeur
etal. 2021)
(S ee alsoworkby R uiPonte C ostaatthis conf!)

Whistle stop tour into t he world of neuron dynamics
Type I/II
Mechanisms
Multiplebiologicalmec hanisms
Analysewithbifurcationtype
Possible roles
Integrator
/ 
resonator
Firing  rate
In pu t current
Firing  rate
In pu t current
Type  I
Type  II
Res pons e
Stimulation  fre q u e n cy

Whistle stop tour into t he world of neuron dynamics
Spatial structure
Mechanisms
Ac tive/passive de ndrites
Locationofinputs
Possible roles
Too manytolist
Stillver yactive, e. g.
Asingle neuroncan solve MNIST(J ones and 
Kording
2021)
Someneurons from neuromorpho.org

Coincidencedetection and exercise
ı [lo}}’}}ˆ˚X

Part 1 
-
Exercise
Tr y toimprove on mysolution.
Competition:best solution presents what theydid.
Divide yourself intopairs /ea ch table candiscuss.

Part 2 
t
(Machine)learning with 
SNNs

Sohow do spiking neural networkslearn?
v’Á˚„Álv}ÁX
Breakitdown intotwoslightlyseparatequestions:
1.
How do biologicalneurons lea rn?
2.
How canwe trainspikingneuralnetworkmodels todotasks?
Ex pec tthese  twoquestions toshed lightonea ch other.
Eachis worthpursuingindepe ndently.
Willfocus primarily on ( 2)in thistutorial.

Biological learning
General approa ches

Strengthen/wea kensyna pses

Add/remove synapses

Add/remove ne urons

Other wildstuff (pa cketsof R NA)?
So me mo dels

STDP

Reward
-
modulated
None of the se workver y wellfor hard tasks.
(Soare theygood modelsof thebrain?)

Solving hard taskswith SNNs
Someidea s thatare stillact ive(the reare ma nyothers)
Rese r voircomputing
(
Maass

Also known as:

Echo statenetworks

Liquidstatemachines
Per formance limitedin pract ice ?
Evolutionary optimisation

Computationallyexpe nsive
Surrogategradient desce nt
(
Zenke

Willcomebac ktothis later

Very brief interlude on artificial neural networks
Input
T
Output
B
:
9T
;
Weight 
matrix
9
Non line ar
Activation
B
Loss
Loss  
fu nction
.
Loss isa big function 
.
à
á
T
whe re 
à
is vec torof a lllea rnable parameters
ı„]Æuµoı]›oÇ
Computegradie ntofloss withrespec t toparameters:  
:
Ï
.
;
Ü

L
!Å
!

Ô
Gradientdescent withlearningrate 
Ù
ã
à
\
à

F
Ù
Ï
.

Very brief interlude on artificial neural networks
Input
T
Output
B
:
9T
;
Weight 
matrix
9
Non line ar
Activation
B
Loss
Loss  
fu nction
.
Chain rule
T
\
Ù
U
\
Ú
V
or
V

L
C
B
T
gives
×í
×ë

L
×í
×ì
—
×ì
×ë
or
V
ñ

L
C
ñ
B
T
—
B
ñ
T
Chaining the chainrule
T
5
\
T
6
\
®
\
T
á
Gives
×
ë
Ù
×
ë
-

L
×
ë
Ù
×
ë
Ù
7
-
—
×
ë
Ù
7
-
×
ë
Ù
7
.
®
×
ë
.
×
ë
-
Vec tor version
T
Ð
9
á
\
Ù
U
Ð
9
à
\
Ú
V
Ð
9
ã
Jacobianmatrix
,
ÜÝ
Ù

L
!
Ù
Ô
!
ë
Õ
Chainrule is 
,
Ú
Ü
Ù

L
,
Ú
,
Ù

Very brief interlude on artificial neural networks
Input
T
Output
B
:
9T
;
Weight 
matrix
9
Non line ar
Activation
B
Loss
Loss  
fu nction
.
Chai n rule
T
\
Ù
U
\
Ú
V
or
V

L
C
B
T
gi ves 
×í
×ë

L
×í
×ì
—
×ì
×ë
or
V
ñ

L
C
ñ
B
T
—
B
ñ
T
Chai ning the chain rule
T
5
\
T
6
\
®
\
T
á
Gi ves
×
ë
Ù
×
ë
-

L
×
ë
Ù
×
ë
Ù
7
-
—
×
ë
Ù
7
-
×
ë
Ù
7
.
®
×
ë
.
×
ë
-
Vector versio n
T
Ð
9
á
\
Ù
U
Ð
9
à
\
Ú
V
Ð
9
ã
Jacobi an  mat ri x
,
ÜÝ
Ù

L
!
Ù
Ô
!
ë
Õ
Cha i nrul e i s 
,
Ú
Ü
Ù

L
,
Ú
,
Ù
Loss i s a bi gf unct i on 
.
à
á
T
where 
à
i s vector of al l l earnabl e parameters
 o ’]( µvı ]ı „] Æuµoı ] ›o Ç
Compute grad i ent of l oss wit h respect  to parameters:   
:
Ï
.
;
Ü

L
!Å
!

Ô
Grad i ent  descent  wit h l earnin grate 
Ù
ã
à
\
à

F
Ù
Ï
.
º
Forgetall this
Autograd
.
Writethe for ward pass,and 
Py Torch
will 
calculateever y thing foryou.
+ better algorithmsthan gradie nt 
descent

Surrogate gradient descent
ı [ı„(’X
Problem
Threshold is 
R

P
s
orHeaviside 
*
:
R

F
s
;
*
ñ
R

L
r
for all 
R

M
r
Gradie nts areall zero.
So lution1/n: sm oo ththresho ld
Huh and 
Se jnowski
(2018)
Works,but slow and notan SNN
So lution2/n: surrogategradientdesc ent
Neftci
etal. (2019)
Only smoothgradie nt(ba ckwardspass)
Ì’Z} Áˆ}˚’X’o}ÁX
Heaviside
Sigmoid
ê
T

L
s
s

E
A
?
	ë

Prospects for the future
So muchworkstilltobe done!
Lots of lowhanging fruit and possible 
questions/projects.
Can we m akethis mo reefficient?

Run faster

Local lea rningversion

Better scaling

Sparseconnectivity
Co mputational advantages ofSN Ns?

Fastdec ision making?

Robusttonoise?

Robusttoadversarialattacks?

More gene ralisable ?

Low power  (ne uromorphiccomputing)
Answer biologicalquestions?

What isthe role ofspikes?
Justene rgyefficie ncy  / transmission?

Local lea rningrule s

Interactionwithsynapse/neuron dynamics

Coding it up in 
PyTorch
ı [o}}’}}ˆ˚X

Crazy idea: massive collaborative project
The surrogategradie ntdesce nt tutorialis 
’}ıZ ˚(}„ ı
myknowledge.
Sound localisationwith surrogategradie nt 
desce nt.
Long histor yof hand c raftedmodelsof 
sound localisationgoingback70 years.
Stillnotresolved!
So couldweturn this intoapape r?
 ÁıZÁ˚[ˆ}X
Lots of separate,somewhatindepe ndent 
Á˚[v˚˚ ıZ˚ lX
„Ì]ˆ˚ 
We write a 250author paper onthis.
Ever yone is welcometocontribute.
Anyone whocontributesa partofa figure or 
sometex tis an author 
(even if this 
eventually getsremoved fromthe paper).
First/lastauthors willbe base d on whoever  
takescha rgeof coordinating ever y thing.All 
other authorsin randomorder.
Ongoing discussions on Discord.
Aimtosubmit somethingin 
6months
?
Will ema ilall participants a link to sign up.

Join the SNUFA community
https://discord. g g /7y8ed2WgS2

Sh ad me hr
Re z a
Pop ulati onC od ing in th e Ce r ebellum
a Ma c hi ne L ea rnin gPer sp ective
April6th
1 5: 00CET

Part 2 
-
Exercise
Fillin themissingpartsofthe code.
Tr y toimprove the model.
Builda version of themodel thatuses regression rather thancla ssification.
Understandhow the solutions ithas found work.
