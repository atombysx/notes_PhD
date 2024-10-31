 >[! Ongoing with acute recordings]
 >4 mice with simultaneous probe (MEC + HVA) and probe (V1 + HPC) 
 >1 mice with only probe (V1+HPC)
 >Currently this set of analysis focuses on *Spatial Modulation in Visual Neurons*

## Are there any spatial modulation?

Seems like it - give some examples.

## How Is Spatial Modulation Measured?
Spatial modulation from 2021 elife mika paper is introduced but additional calculations are used:
1. Landmark positions are calculated first based on receptive field from sparse noise stimulus. A video of the VR at all positions is fed to the receptive field to check where the landmarks are in position. e.g. first landmark X is set to 30cm in BONSAI but based on the receptive, peripheral visual field might have them at 26cm.
2. The responses are first averaged and normalized at [0,1] range from odd and even laps seperately
3. Peaks are found by findpeaks() with minimum 0.3 and peak distance 17 on the odd laps averages.
4. Search for the peak at the landmark locations within [-10,10] range.
5. Find which of two peaks is highest and is termed as preferred and the other is non-preferred
6. SMI is then calculated from $$ SMI_{even} = \frac{R_{even , prefer} - R_{even , nonprefer}}{R_{even,prefer} + R_{even,nonprefer}}$$
 7. Repeat the same for even vs odd.
 8. Take the average of both $$ SMI = \frac{SMI_{odd}+SMI_{even}}{2} $$
Other approaches:

1. Just do very simple scatter plots for peak firing rate to landmark R1 vs landmark R2 and if no spatial modulation, it should be a y = x line.
2. Paired t test between firing rate to R1 vs R2
## How Many V1 (HVA) neurons are modulated?




## Are t1 and t2 modulations independent?

P(t1|t2) & P(t2|t1) high? For neurons modulated in t1, same for t2 or not much?
Seems not correlated or anti-correlated. Neurons modulated in T1/T2 for Bs dont have 

## Are there different types of modulations?

## How About Bs? They are shared between T1 and T2
Calculate Residual Response Ratio:
 $$ Residual Ratio = \frac{R_{B}-R_{mean}}{R_{mean}} $$
for each B of B1, B2, B3, B4.

Check the correlation between them and might show contextual difference.

Check different types of modulation.

Seems like there are some anti-correlations between the ratios in the two tracks.

Is there a strong contextual modulation and how do we test it?

Interesting thought: can we actually use MEC representation to predict the contextual modulation on plaids?

Also discussed about control, the novelty and reward zone can be influencing the responses to the plaids so might need to control studies.