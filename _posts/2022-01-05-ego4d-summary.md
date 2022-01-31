---
layout: distill
title: "Dataset Summary: Ego4D"
description: Notes on the recently announced Ego4D dataset  
date: 2022-01-05

authors:
  - name: Akkapaka Saikiran
	url: "https://akkapakasaikiran.github.io/" 
	affiliations:
	  name: CSE, IIT Bombay

---

Resources: 
[Website](https://ego4d-data.org/) | 
[ArXiv](https://arxiv.org/abs/2110.07058) | 
[Release video](https://www.youtube.com/watch?v=2dau0W0NVQY)

**What is it?** 
"A massive-scale, egocentric dataset and benchmark suite collected across 74 worldwide locations and 9 countries [855 unique camera wearers], with over 3,025 hours of daily-life activity video." 
People wear cameras (head-mounted) and record activities like walking, cooking, cleaning, etc. These videos are mostly unscripted and 'in the wild'.

**Motivation.** 
Computer Vision has come very far by using internet images (and videos) for its datasets (eg. ImageNet, Kinetics, MS COCO, etc.). 
But these datasets are well-curated, disembodied, in isolated moments of time, and in the third-person view. 
These limitations hamper progress in robot learning and augmented reality research. 
Ego4D provides uncurated, multimodal, first-person streams of data that depend on agents’ attention and actions.

**Novelty.** 
Some existing egocentric datasets: EPIC-Kitchens, UT Ego, EGTEA Gaze+, etc. 
Ego4D improves on the scale (no. of hours of video as well as no. of participants), diversity (74 locations), and realism.

**Dataset details.** 
People wore cameras for 1-10 hrs ⇒ long-form videos capturing many activities (many of which are probably mundane). 
"Portions of the dataset also provide audio, 3D mesh scans, gaze, stereo, and/or synchronized multi-camera views". 
Multiple cameras are used, and this variety gives rise to different fields of view (eg. some look down on hands, others look ahead). 
2207 hours from the total 3025 hours have audio associated with the videos.

**Narrations.** 
All videos have temporally dense narrations (on average 13.2 sentences per minute of video) associated with them that describe the activities taking place (on average 7.4 words long). 
These narrations are manually annotated and amount to 3.85M sentences in total containing 1772 unique verbs (actions) and 4336 unique nouns (objects). 
Videos are also divided into 5 min clips that have a multiple-sentence summary associated with them. 
Ego4D can thus be viewed as a large-scale dataset of aligned language and video, similar to HowTo100M. 
It thus gives way to many grounded vision-language tasks like retrieval and captioning. 

**Benchmarks.** 
Egocentric vision demands novel approaches of video understanding to account for long-form video, attention cues, person-object interaction, multi-sensory data, and the lack of manual temporal curation inherent to a passively worn camera. To this end, Ego4D comes with a set of benchmark tasks and associated baseline models that use SoTA components. 
The benchmarks are: 1) Episodic Memory, 2) Hands and Objects, 3) Audio-visual Diarization, 4. Social Interactions, and 5) Forecasting.


