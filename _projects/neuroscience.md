---
layout: page
title: topology & neuroscience
description: A topological approach to neural encoding
img: assets/img/neuro_image.png
importance: 1
category: research
---

What does it mean for there to be circular structures in neural activity? 

Consider a collection of images with different orientations shown in Figure 1A. The red and dark orange images have high similarity, whereas the red and green images have low similarity. What would happen if we arranged the eight images in a way that respects this similarity? The images would be arranged in a circular fashion, as shown in Figure 1B. 


<p align="center">
  <img width="750" src="https://irisyoon.com/assets/img/neuro_cyclic_structures.png">
</p>
<div class="caption">
	Figure 1. Circular structure of data. <span style="font-weight:bold">A.</span> Collection of images. <span style="font-weight:bold">B.</span> An arrangement of images based on the similarity of orientation reveals a circular structure. <span style="font-weight:bold">C.</span> Collection of neural activities (spike trains). <span style="font-weight:bold">D.</span> Consider two spike trains to be similar if the vertical lines are well-aligned after "sliding" one spike train by a small amount. An arrangement of neural activity based on spike train similarity reveals a circular structure. 
</div>


Similarly, consider a collection of neural activities (called spike trains) shown in Figure 1C. Each row indicates the activity of a single neuron over some time period. The vertical line indicates the neuron's firing at a corresponding time. If we observe the neuron for, say $$ M $$ time intervals, then each spike train is a binary vector in $$ \mathbb{R}^M $$. Given two spike trains $$ s_1 $$ and $$ s_2 $$, let's measure similarities between two spike trains as the amount one needs to "slide" $$ s_1 $$ to "match" with $$ s_2 $$. Then, the red spike train is similar to the dark orange spike train, but it is quite dissimilar to the green spike train. Again, if we were to arrange the spike trains in a way that respects this similarity, we would arrange them in a cyclic manner (Figure 1D). 

Now, suppose there are many images and long spike trains that we cannot make the arrangements by hand. How would a computer recognize that these high-dimensional data contain cyclic structures? Let $$ P $$ denote the point cloud representing a system of interest, such as the collection of stimulus or neural activity. We calculate the similarity between every pair of elements in the system. We construct a representation of the system as we vary the similarity level by a sequence of simplicial complexes. The loops in this sequence are summarized by a persistence diagram, where the points far from the diagonal represent the large loops. See the following figure. 

<p align="center">
  <img width="750" src="https://irisyoon.com/assets/img/neural_PH.png">
</p>
<div class="caption">
	Figure 2. Detecting circular structures from high dimensional data. Given the data (either images or spike trains), we first compute a matrix encoding pairwise similarity between all elements in the system. We then create the sequence of simplicial complexes that represents the connectivity of the system at various similarity values. Finally, we summarize the loops in the simplicial complexes using a persistence diagram. Points far from the diagonal represent significant structures.
</div>


So far, we have seen that persistence diagrams can indicate if a collection of images or spike trains contain circular structures. Consider a hypothetical experiment in which we present a stimulus video to a mouse while measuring its neural activity. Let's assume that the persistence diagram indicates that there are two circular structures in the stimulus and one circular structure in the neural activity. Is the unique circular feature in the neural activity reflecting one of the circular features in the stimulus? If so, which one? Such questions are topological manifestations of fundamental problems in neuroscience called neural encoding that study how neurons represent information. 


<p align="center">
  <img width="450" src="https://irisyoon.com/assets/img/encoding.png">
</p>
<div class="caption">
	Figure 3. Neural encoding, stated as a problem in topology. Consider an experiment in which we present some stimulus while measuring neural activity. The persistence diagrams indicate that there are two circular features in the stimulus while there is only one circular feature in the neural activity. Which feature of the stimulus is represented by the neurons?
</div>

To address the above questions, I developed a framework for comparing persistence diagrams called the <a href="https://arxiv.org/abs/2201.05190">analogous bars method</a>.

The methods paper has been accepted in the Journal of Applied and Computational Topology, conditional on minor revisions. A follow-up paper implementing the method on simulated and experimental neuroscience datasets is under preparation.

Preprint: <a href="https://arxiv.org/abs/2201.05190">Persistent Extension and Analogous Bars: Data-Induced Relations Between Persistence Barcodes</a>.

Code: <a href="https://github.com/UDATG/analogous_bars">github: analogous bars</a>

*Joint work with <a href="http://www.chadgiusti.com/">Chad Giusti</a> (U. Delaware) and <a href="https://www.math.upenn.edu/~ghrist/">Robert Ghrist</a> (U. Penn).*


