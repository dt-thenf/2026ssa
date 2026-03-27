# Activity recognition

*Article · Talk · Read · Edit · View history*

From Wikipedia, the free encyclopedia

> This article is written like a research paper or a scientific journal. Please help rewrite it in a neutral, encyclopedic style and simplify overly technical phrases. (March 2018)

Activity recognition aims to recognize the actions and goals of one or more agents from a series of observations on the agents' actions and the environmental conditions. Since the 1980s, this research field has captured the attention of several computer science communities due to its strength in providing personalized support for many different applications and its connection to many different fields of study such as medicine, human-computer interaction, or sociology.

Due to its multifaceted nature, different fields may refer to activity recognition as plan recognition, goal recognition, intent recognition, behavior recognition, location estimation and location-based services.

## Types

### Sensor-based, single-user activity recognition

Sensor-based activity recognition integrates the emerging area of sensor networks with novel data mining and machine learning techniques to model a wide range of human activities.[1][2] Mobile devices (e.g. smart phones) provide sufficient sensor data and calculation power to enable physical activity recognition to provide an estimation of the energy consumption during everyday life. Sensor-based activity recognition researchers believe that by empowering ubiquitous computers and sensors to monitor the behavior of agents (under consent), these computers will be better suited to act on our behalf. Visual sensors that incorporate color and depth information, such as the Kinect, allow more accurate automatic action recognition and fuse many emerging applications such as interactive education[3] and smart environments.[4] Multiple views of visual sensor enable the development of machine learning for automatic view invariant action recognition.[5] More advanced sensors used in 3D motion capture systems allow highly accurate automatic recognition, in the expenses of more complicated hardware system setup.[6]

### Levels of sensor-based activity recognition

Sensor-based activity recognition is a challenging task due to the inherent noisy nature of the input. Thus, statistical modeling has been the main thrust in this direction in layers, where the recognition at several intermediate levels is conducted and connected. At the lowest level where the sensor data are collected, statistical learning concerns how to find the detailed locations of agents from the received signal data. At an intermediate level, statistical inference may be concerned about how to recognize individuals' activities from the inferred location sequences and environmental conditions at the lower levels. Furthermore, at the highest level, a major concern is to find out the overall goal or subgoals of an agent from the activity sequences through a mixture of logical and statistical reasoning.

### Sensor-based, multi-user activity recognition

Recognizing activities for multiple users using on-body sensors first appeared in the work by ORL using active badge systems[7] in the early 1990s. Other sensor technology such as acceleration sensors were used for identifying group activity patterns during office scenarios.[8] Activities of Multiple Users in intelligent environments are addressed in Gu et al.[9] In this work, they investigate the fundamental problem of recognizing activities for multiple users from sensor readings in a home environment, and propose a novel pattern mining approach to recognize both single-user and multi-user activities in a unified solution.

### Sensor-based group activity recognition

Recognition of group activities is fundamentally different from single, or multi-user activity recognition in that the goal is to recognize the behavior of the group as an entity, rather than the activities of the individual members within it.[10] Group behavior is emergent in nature, meaning that the properties of the behavior of the group are fundamentally different than the properties of the behavior of the individuals within it, or any sum of that behavior.[11] The main challenges are in modeling the behavior of the individual group members, as well as the roles of the individual within the group dynamic[12] and their relationship to emergent behavior of the group in parallel.[13] Challenges which must still be addressed include quantification of the behavior and roles of individuals who join the group, integration of explicit models for role description into inference algorithms, and scalability evaluations for very large groups and crowds. Group activity recognition has applications for crowd management and response in emergency situations, as well as for social networking and Quantified Self applications.[14]

## Approaches

### Activity recognition through logic and reasoning

Logic-based approaches keep track of all logically consistent explanations of the observed actions. Thus, all possible and consistent plans or goals must be considered. Kautz provided a formal theory of plan recognition. He described plan recognition as a logical inference process of circumscription. All actions and plans are uniformly referred to as goals, and a recognizer's knowledge is represented by a set of first-order statements, called event hierarchy. Event hierarchy is encoded in first-order logic, which defines abstraction, decomposition and functional relationships between types of events.[15]

Kautz's general framework for plan recognition has an exponential time complexity in worst case, measured in the size of the input hierarchy. Lesh and Etzioni went one step further and presented methods in scaling up goal recognition to scale up his work computationally. In contrast to Kautz's approach where the plan library is explicitly represented, Lesh and Etzioni's approach enables automatic plan-library construction from domain primitives. Furthermore, they introduced compact representations and efficient algorithms for goal recognition on large plan libraries.[16]

Inconsistent plans and goals are repeatedly pruned when new actions arrive. Besides, they also presented methods for adapting a goal recognizer to handle individual idiosyncratic behavior given a sample of an individual's recent behavior. Pollack et al. described a direct argumentation model that can know about the relative strength of several kinds of arguments for belief and intention description.

A serious problem of logic-based approaches is their inability or inherent infeasibility to represent uncertainty. They offer no mechanism for preferring one consistent approach to another and are incapable of deciding whether one particular plan is more likely than another, as long as both of them can be consistent enough to explain the actions observed. There is also a lack of learning ability associated with logic based methods.

Another approach to logic-based activity recognition is to use stream reasoning based on answer set programming,[17] and has been applied to recognising activities for health-related applications,[18] which uses weak constraints to model a degree of ambiguity/uncertainty.

### Activity recognition through probabilistic reasoning

Probability theory and statistical learning models are more recently applied in activity recognition to reason about actions, plans and goals under uncertainty.[19] In the literature, there have been several approaches which explicitly represent uncertainty in reasoning about an agent's plans and goals.

Using sensor data as input, Hodges and Pollack designed machine learning-based systems for identifying individuals as they perform routine daily activities such as making coffee.[20] Intel Research (Seattle) Lab and University of Washington at Seattle have done some important works on using sensors to detect human plans.[21][22][23] Some of these works infer user transportation modes from readings of radio-frequency identifiers (RFID) and global positioning systems (GPS).

The use of temporal probabilistic models has been shown to perform well in activity recognition and generally outperform non-temporal models.[24] Generative models such as the Hidden Markov Model (HMM) and the more generally formulated Dynamic Bayesian Networks (DBN) are popular choices in modelling activities from sensor data.[25][26][27][28] Discriminative models such as Conditional Random Fields (CRF) are also commonly applied and also give good performance in activity recognition.[29][30]

Generative and discriminative models both have their pros and cons and the ideal choice depends on their area of application. A dataset together with implementations of a number of popular models (HMM, CRF) for activity recognition can be found here.

Conventional temporal probabilistic models such as the hidden Markov model (HMM) and conditional random fields (CRF) model directly model the correlations between the activities and the observed sensor data. In recent years, increasing evidence has supported the use of hierarchical models which take into account the rich hierarchical structure that exists in human behavioral data.[26][31][32] The core idea here is that the model does not directly correlate the activities with the sensor data, but instead breaks the activity into sub-activities (sometimes referred to as actions) and models the underlying correlations accordingly. An example could be the activity of preparing a stir fry, which can be broken down into the subactivities or actions of cutting vegetables, frying the vegetables in a pan and serving it on a plate. Examples of such a hierarchical model are Layered Hidden Markov Models (LHMMs)[31] and the hierarchical hidden Markov model (HHMM), which have been shown to significantly outperform its non-hierarchical counterpart in activity recognition.[26]

### Data mining based approach to activity recognition

Different from traditional machine learning approaches, an approach based on data mining has been recently proposed. In the work of Gu et al., the problem of activity recognition is formulated as a pattern-based classification problem. They proposed a data mining approach based on discriminative patterns which describe significant changes between any two activity classes of data to recognize sequential, interleaved and concurrent activities in a unified solution.[33] Gilbert et al. use 2D corners in both space and time. These are grouped spatially and temporally using a hierarchical process, with an increasing search area. At each stage of the hierarchy, the most distinctive and descriptive features are learned efficiently through data mining (Apriori rule).[34]

### GPS-based activity recognition

Location-based activity recognition can also rely on GPS data to recognize activities.[35][36]

## Sensor usage

### Vision-based activity recognition

It is a very important and challenging problem to track and understand the behavior of agents through videos taken by various cameras. The primary technique employed is Computer Vision. Vision-based activity recognition has found many applications such as human-computer interaction, user interface design, robot learning, and surveillance, among others. Scientific conferences where vision based activity recognition work often appears are ICCV and CVPR.

In vision-based activity recognition, a great deal of work has been done. Researchers have attempted a number of methods such as optical flow, Kalman filtering, Hidden Markov models, etc., under different modalities such as single camera, stereo, and infrared. In addition, researchers have considered multiple aspects on this topic, including single pedestrian tracking, group tracking, and detecting dropped objects.

Recently some researchers have used RGBD cameras like Microsoft Kinect to detect human activities.[37] Depth cameras add extra dimension i.e. depth which normal 2d camera fails to provide. Sensory information from these depth cameras have been used to generate real-time skeleton model of humans with different body positions.[38] This skeleton information provides meaningful information that researchers have used to model human activities which are trained and later used to recognize unknown activities.[39][40]

With the recent emergency of deep learning, RGB video based activity recognition has seen rapid development. It uses videos captured by RGB cameras as input and perform several tasks, including: video classification, detection of activity start and end in videos, and spatial-temporal localization of activity and the people performing the activity.[41] Pose estimation methods[42] allow extracting more representative skeletal features for action recognition.[43] That said, it has been discovered that deep learning based action recognition may suffer from adversarial attacks, where an attacker alter the input insignificantly to fool an action recognition system.[44]

Despite remarkable progress of vision-based activity recognition, its usage for most actual visual surveillance applications remains a distant aspiration.[45] Conversely, the human brain seems to have perfected the ability to recognize human actions. This capability relies not only on acquired knowledge, but also on the aptitude of extracting information relevant to a given context and logical reasoning. Based on this observation, it has been proposed to enhance vision-based activity recognition systems by integrating commonsense reasoning and, contextual and commonsense knowledge.

### Hierarchical Human Activity (HAR) Recognition

Hierarchical human activity recognition is a technique within computer vision and machine learning. It aims to identify and comprehend human actions or behaviors from visual data. This method entails structuring activities hierarchically, creating a framework that represents connections and interdependencies among various actions.[46] HAR techniques can be used to understand data correlations and model fundamentals to improve models, to balance accuracy and privacy concerns in sensitive application areas, and to identify and manage trivial labels that have no relevance in specific use cases.[47]

### Levels of vision-based activity recognition

In vision-based activity recognition, the computational process is often divided into four steps, namely human detection, human tracking, human activity recognition and then a high-level activity evaluation.

### Fine-grained action localization

*Main article: Object co-segmentation*

In computer vision-based activity recognition, fine-grained action localization typically provides per-image segmentation masks delineating the human object and its action category (e.g., Segment-Tube[48]). Techniques such as dynamic Markov Networks, CNN and LSTM are often employed to exploit the semantic correlations between consecutive video frames. Geometric fine-grained features such as objective bounding boxes and human poses facilitate activity recognition with graph neural network.[41][49]

### Automatic gait recognition

*Main article: Gait recognition*

One way to identify specific people is by how they walk. Gait-recognition software can be used to record a person's gait or gait feature profile in a database for the purpose of recognizing that person later, even if they are wearing a disguise.

### Wi-Fi-based activity recognition

When activity recognition is performed indoors and in cities using the widely available Wi-Fi signals and 802.11 access points, there is much noise and uncertainty. These uncertainties can be modeled using a dynamic Bayesian network model.[50] In a multiple goal model that can reason about user's interleaving goals, a deterministic state transition model is applied.[51] Another possible method models the concurrent and interleaving activities in a probabilistic approach.[52] A user action discovery model could segment Wi-Fi signals to produce possible actions.[53]

### Basic models of Wi-Fi recognition

One of the primary thought of Wi-Fi activity recognition is that when the signal goes through the human body during transmission; which causes reflection, diffraction, and scattering. Researchers can get information from these signals to analyze the activity of the human body.

#### Static transmission model

As shown in,[54] when wireless signals are transmitted indoors, obstacles such as walls, the ground, and the human body cause various effects such as reflection, scattering, diffraction, and diffraction. Therefore, receiving end receives multiple signals from different paths at the same time, because surfaces reflect the signal during the transmission, which is known as multipath effect.

The static model is based on these two kinds of signals: the direct signal and the reflected signal. Because there is no obstacle in the direct path, direct signal transmission can be modeled by Friis transmission equation:

```text
Pr = Pt * Gt * Gr * λ^2 / ((4π)^2 * d^2)
```

Where:

- `Pt` is the power fed into the transmitting antenna input terminals
- `Pr` is the power available at receiving antenna output terminals
- `d` is the distance between antennas
- `Gt` is transmitting antenna gain
- `Gr` is receiving antenna gain
- `λ` is the wavelength of the radio frequency

If we consider the reflected signal, the new equation is:

```text
Pr = Pt * Gt * Gr * λ^2 / ((4π)^2 * (d + 4h)^2)
```

Where `h` is the distance between reflection points and direct path.

When human shows up, we have a new transmission path. Therefore, the final equation is:

```text
Pr = Pt * Gt * Gr * λ^2 / ((4π)^2 * (d + 4h + Δ)^2)
```

Where `Δ` is the approximate difference of the path caused by human body.

#### Dynamic transmission model

In this model, we consider the human motion, which causes the signal transmission path to change continuously. We can use Doppler Shift to describe this effect, which is related to the motion speed.

```text
Δf = (2v cosθ / c) f
```

By calculating the Doppler Shift of the receiving signal, we can figure out the pattern of the movement, thereby further identifying human activity. For example, in,[55] the Doppler shift is used as a fingerprint to achieve high-precision identification for nine different movement patterns.

#### Fresnel zone

The Fresnel zone was initially used to study the interference and diffraction of the light, which is later used to construct the wireless signal transmission model. Fresnel zone is a series of elliptical intervals whose foci are the positions of the sender and receiver.

When a person is moving across different Fresnel zones, the signal path formed by the reflection of the human body changes, and if people move vertically through Fresnel zones, the change of signal will be periodic. In a pair of papers, Wang et.al. applied the Fresnel model to the activity recognition task and got a more accurate result.[56][57]

#### Modeling of the human body

In some tasks, we should consider modeling the human body accurately to achieve better results. For example,[57] described the human body as concentric cylinders for breath detection. The outside of the cylinder denotes the rib cage when people inhale, and the inside denotes that when people exhale. So the difference between the radius of that two cylinders represents the moving distance during breathing. The change of the signal phases can be expressed in the following equation:

```text
θ = 2π * (2Δd / λ)
```

Where:

- `θ` is the change of the signal phases
- `λ` is the wavelength of the radio frequency
- `Δd` is moving distance of rib cage

## Datasets

There are some popular datasets that are used for benchmarking activity recognition or action recognition algorithms.

- **UCF-101**: It consists of 101 human action classes, over 13k clips and 27 hours of video data. Action classes include applying makeup, playing dhol, cricket shot, shaving beard, etc.[58]
- **HMDB51**: This is a collection of realistic videos from various sources, including movies and web videos. The dataset is composed of 6,849 video clips from 51 action categories (such as “jump”, “kiss” and “laugh”), with each category containing at least 101 clips.[59]
- **Kinetics**: This is a significantly larger dataset than the previous ones. It contains 400 human action classes, with at least 400 video clips for each action. Each clip lasts around 10s and is taken from a different YouTube video. This dataset was created by DeepMind.[60]

## Applications

By automatically monitoring human activities, home-based rehabilitation can be provided for people suffering from traumatic brain injuries. One can find applications ranging from security-related applications and logistics support to location-based services.[61] Activity recognition systems have been developed for wildlife observation[62] and energy conservation in buildings.[63]

## See also

- AI effect
- Applications of artificial intelligence
- Conditional random field
- Gesture recognition
- Hidden Markov model
- Motion analysis
- Naive Bayes classifier
- Support vector machines
- Object co-segmentation
- Outline of artificial intelligence
- Video content analysis

## References

1. Tanzeem Choudhury, Gaetano Borriello, et al. *The Mobile Sensing Platform: An Embedded System for Activity Recognition*. Appears in the IEEE Pervasive Magazine – Special Issue on Activity-Based Computing, April 2008.
2. Nishkam Ravi, Nikhil Dandekar, Preetham Mysore, Michael Littman. *Activity Recognition from Accelerometer Data*. Proceedings of the Seventeenth Conference on Innovative Applications of Artificial Intelligence (IAAI/AAAI 2005).
3. Yang, Yang; Leung, Howard; Shum, Hubert P. H.; Li, Jiao; Zeng, Lanling; Aslam, Nauman; Pan, Zhigeng (2018). "CCESK: A Chinese Character Educational System Based on Kinect". *IEEE Transactions on Learning Technologies*. 11 (3): 342–347. Bibcode:2018ITLT...11..342Y. doi:10.1109/TLT.2017.2723888. S2CID 52899136.
4. Ho, Edmond S. L.; Chan, Jacky C. P.; Chan, Donald C. K.; Shum, Hubert P. H.; Cheung, Yiu-ming; Yuen, P. C. (2016). "Improving Posture Classification Accuracy for Depth Sensor-based Human Activity Monitoring in Smart Environments". *Computer Vision and Image Understanding*. 148: 97–110. doi:10.1016/j.cviu.2015.12.011. S2CID 207060860.
5. Zhang, Jingtian; Shum, Hubert P. H.; Han, Jungong; Shao, Ling (2018). "Action Recognition from Arbitrary Views Using Transferable Dictionary Learning". *IEEE Transactions on Image Processing*. 27 (10): 4709–4723. Bibcode:2018ITIP...27.4709Z. doi:10.1109/TIP.2018.2836323. PMID 29994770. S2CID 49536771.
6. Shen, Yijun; Yang, Longzhi; Ho, Edmond S. L.; Shum, Hubert P. H. (2020). "Interaction-based Human Activity Comparison". *IEEE Transactions on Visualization and Computer Graphics*. 26 (8): 115673–115684. Bibcode:2020ITVCG..26.2620S. doi:10.1109/TVCG.2019.2893247. PMID 30703028. S2CID 73447673.
7. Want R., Hopper A., Falcao V., Gibbons J.: *The Active Badge Location System*, ACM Transactions on Information, Systems, Vol. 40, No. 1, pp. 91–102, January 1992.
8. Bieber G., Kirste T., *Untersuchung des gruppendynamischen Aktivitaetsverhaltes im Office-Umfeld*, 7. Berliner Werkstatt Mensch-Maschine-Systeme, Berlin, Germany, 2007.
9. Tao Gu, Zhanqing Wu, Liang Wang, Xianping Tao, and Jian Lu. *Mining Emerging Patterns for Recognizing Activities of Multiple Users in Pervasive Computing*. In Proc. of the 6th International Conference on Mobile and Ubiquitous Systems: Computing, Networking and Services (MobiQuitous '09), Toronto, Canada, July 13–16, 2009.
10. Dawud Gordon, Jan-Hendrik Hanne, Martin Berchtold, Ali Asghar Nazari Shirehjini, Michael Beigl: *Towards Collaborative Group Activity Recognition Using Mobile Devices*, Mobile Networks and Applications 18(3), 2013, pp. 326–340.
11. Lewin, K. *Field theory in social science: selected theoretical papers*. Social science paperbacks. Harper, New York, 1951.
12. Hirano, T., and Maekawa, T. *A hybrid unsupervised/supervised model for group activity recognition*. In Proceedings of the 2013 International Symposium on Wearable Computers, ISWC ’13, ACM (New York, NY, USA, 2013), 21–24.
13. Brdiczka, O., Maisonnasse, J., Reignier, P., and Crowley, J. L. *Detecting small group activities from multimodal observations*. Applied Intelligence 30, 1 (July 2007), 47–57.
14. Dawud Gordon, *Group Activity Recognition Using Wearable Sensing Devices*, Dissertation, Karlsruhe Institute of Technology, 2014.
15. H. Kautz. *A formal theory of plan recognition*. In PhD thesis, University of Rochester, 1987.
16. N. Lesh and O. Etzioni. *A sound and fast goal recognizer*. In Proceedings of the International Joint Conference on Artificial Intelligence, 1995.
17. Do, Thang; Seng W. Loke; Fei Liu (2011). "Answer Set Programming for Stream Reasoning". *Advances in Artificial Intelligence*. Lecture Notes in Computer Science. Vol. 6657. pp. 104–109. CiteSeerX 10.1.1.453.2348. doi:10.1007/978-3-642-21043-3_13. ISBN 978-3-642-21042-6.
18. Do, Thang; Seng W. Loke; Fei Liu (2012). "HealthyLife: an Activity Recognition System with Smartphone using Logic-Based Stream Reasoning" (PDF). Proceedings of the 9th International Conference on Mobile and Ubiquitous Systems: Computing, Networking and Services, (Mobiquitous 2012).
19. E. Charniak and R.P. Goldman. *A Bayesian model of plan recognition*. Artificial Intelligence, 64:53–79, 1993.
20. M.R. Hodges and M.E. Pollack. *An 'object-use fingerprint': The use of electronic sensors for human identification*. In Proceedings of the 9th International Conference on Ubiquitous Computing, 2007.
21. Mike Perkowitz, Matthai Philipose, Donald J. Patterson, and Kenneth P. Fishkin. *Mining models of human activities from the web*. In Proceedings of the Thirteenth International World Wide Web Conference (WWW 2004), pages 573–582, May 2004.
22. Matthai Philipose, Kenneth P. Fishkin, Mike Perkowitz, Donald J. Patterson, Dieter Fox, Henry Kautz, and Dirk Hähnel. *Inferring activities from interactions with objects*. In IEEE Pervasive Computing, pages 50–57, October 2004.
23. Dieter Fox Lin Liao, Donald J. Patterson and Henry A. Kautz. *Learning and inferring transportation routines*. Artif. Intell., 171(5–6):311–331, 2007.
24. TLM van Kasteren, Gwenn Englebienne, BJA Kröse. *Human activity recognition from wireless sensor network data: Benchmark and software.* Activity Recognition in Pervasive Intelligent Environments, 165–186, Atlantis Press.
25. Piyathilaka, L.; Kodagoda, S. "Gaussian mixture based HMM for human daily activity recognition using 3D skeleton features," Industrial Electronics and Applications (ICIEA), 2013 8th IEEE Conference on, vol., no., pp.567,572, 19–21 June 2013.
26. TLM van Kasteren, Gwenn Englebienne, Ben Kröse. *Hierarchical Activity Recognition Using Automatically Clustered Actions*, 2011, Ambient Intelligence, 82–91, Springer Berlin/Heidelberg.
27. Daniel Wilson and Chris Atkeson. *Simultaneous tracking and activity recognition (STAR) using many anonymous binary sensors.* In Proceedings of the 3rd international conference on Pervasive Computing, Pervasive, pages 62–79, Munich, Germany, 2005.
28. Nuria Oliver, Barbara Rosario and Alex Pentland. *A Bayesian Computer Vision System for Modeling Human Interactions*. Appears in PAMI Special Issue on Visual Surveillance and Monitoring, Aug 00.
29. TLM Van Kasteren, Athanasios Noulas, Gwenn Englebienne, Ben Kröse, *Accurate activity recognition in a home setting*, 2008/9/21, Proceedings of the 10th international conference on Ubiquitous computing, 1–9, ACM.
30. Derek Hao Hu, Sinno Jialin Pan, Vincent Wenchen Zheng, Nathan NanLiu, and Qiang Yang. *Real world activity recognition with multiple goals*. In Proceedings of the 10th international conference on Ubiquitous computing, Ubicomp, pages 30–39, New York, NY, USA, 2008. ACM.
31. Nuria Oliver, Ashutosh Garg, and Eric Horvitz. *Layered representations for learning and inferring office activity from multiple sensory channels*. Comput. Vis. Image Underst., 96(2):163–180, 2004.
32. Amarnag Subramanya, Alvin Raj, Jeff Bilmes, and Dieter Fox. *Hierarchical models for activity recognition*. In Proceedings of the international conference on Multimedia Signal Processing, MMSP, Victoria, CA, October 2006.
33. Tao Gu, Zhanqing Wu, Xianping Tao, Hung Keng Pung, and Jian Lu. *epSICAR: An Emerging Patterns based Approach to Sequential, Interleaved and Concurrent Activity Recognition*. In Proc. of the 7th Annual IEEE International Conference on Pervasive Computing and Communications (Percom '09), Galveston, Texas, March 9–13, 2009.
34. Gilbert A, Illingworth J, Bowden R. *Action Recognition using Mined Hierarchical Compound Features*. IEEE Trans Pattern Analysis and Machine Learning.
35. Liao, Lin, Dieter Fox, and Henry Kautz. "Hierarchical conditional random fields for GPS-based activity recognition." *Robotics Research*. Springer, Berlin, Heidelberg, 2007. 487–506.
36. Liao, Lin, Dieter Fox, and Henry Kautz. "Location-based activity recognition." *Advances in Neural Information Processing Systems*. 2006.
37. Ho, Edmond S. L.; Chan, Jacky C. P.; Chan, Donald C. K.; Shum, Hubert P. H.; Cheung, Yiu-ming; Yuen, P. C. (2016). "Improving Posture Classification Accuracy for Depth Sensor-Based Human Activity Monitoring in Smart Environments". *Computer Vision and Image Understanding*. 148. Elsevier: 97–110. doi:10.1016/j.cviu.2015.12.011. ISSN 1077-3142.
38. Shum, Hubert P. H.; Ho, Edmond S. L.; Jiang, Yang; Takagi, Shu (2013). "Real-Time Posture Reconstruction for Microsoft Kinect". *IEEE Transactions on Cybernetics*. 43 (5). IEEE: 1357–1369. Bibcode:2013ITCyb..43.1357S. doi:10.1109/TCYB.2013.2275945. ISSN 2168-2267. PMID 23981562. S2CID 14124193.
39. Piyathilaka, L.; Kodagoda, S. "Gaussian mixture based HMM for human daily activity recognition using 3D skeleton features," Industrial Electronics and Applications (ICIEA), 2013 8th IEEE Conference on, vol., no., pp.567, 572, 19–21 June 2013.
40. Piyathilaka, L. and Kodagoda, S., 2015. *Human activity recognition for domestic robots*. In Field and Service Robotics (pp. 395–408). Springer, Cham.
41. Qiao, Tanqiu; Men, Qianhui; Li, Frederick W. B.; Kubotani, Yoshiki; Morishima, Shigeo; Shum, Hubert P. H. (2022). *Geometric Features Informed Multi-person Human-object Interaction Recognition in Videos*. Lecture Notes in Computer Science. Vol. 13664. Springer. pp. 474–491. arXiv:2207.09425. doi:10.1007/978-3-031-19772-7_28. ISBN 978-3-031-19772-7.
42. Huang, Ying; Shum, Hubert P. H.; Ho, Edmond S. L.; Aslam, Nauman (2020). "High-Speed Multi-Person Pose Estimation with Deep Feature Transfer". *Computer Vision and Image Understanding*. 197–198 103010. Elsevier. doi:10.1016/j.cviu.2020.103010. ISSN 1077-3142. S2CID 219905793.
43. Men, Qianhui; Ho, Edmond S. L.; Shum, Hubert P. H.; Leung, Howard (2023). "Focalized Contrastive View-Invariant Learning for Self-Supervised Skeleton-Based Action Recognition". *Neurocomputing*. 537. Elsevier: 198–209. arXiv:2304.00858. doi:10.1016/j.neucom.2023.03.070. ISSN 0925-2312.
44. Lu, Zhengzhi; Wang, He; Chang, Ziyi; Yang, Guoan; Shum, Hubert P. H. (2023). *Hard No-Box Adversarial Attack on Skeleton-Based Human Action Recognition with Skeleton-Motion-Informed Gradient*. IEEE/CVF. arXiv:2308.05681.
45. Bux, Allah; Angelov, Plamen; Habib, Zulfiqar (2017). "A comprehensive review on handcrafted and learning-based action representation approaches for human activity recognition". *Applied Sciences*. 7 (1): 110. doi:10.3390/app7010110.
46. Aggarwal, J.K.; Ryoo, M.S. (2011-04-29). "Human activity analysis: A review". *ACM Computing Surveys*. 43 (3): 16:1–16:43. doi:10.1145/1922649.1922653. ISSN 0360-0300. S2CID 5388357.
47. Altın, Mahsun; Gürsoy, Furkan; Xu, Lina (2021). "Machine-Generated Hierarchical Structure of Human Activities to Reveal How Machines Think". *IEEE Access*. 9: 18307–18317. arXiv:2101.07855. Bibcode:2021IEEEA...918307A. doi:10.1109/ACCESS.2021.3053084. ISSN 2169-3536.
48. Wang, Le; Duan, Xuhuan; Zhang, Qilin; Niu, Zhenxing; Hua, Gang; Zheng, Nanning (2018-05-22). "Segment-Tube: Spatio-Temporal Action Localization in Untrimmed Videos with Per-Frame Segmentation" (PDF). *Sensors*. 18 (5): 1657. Bibcode:2018Senso..18.1657W. doi:10.3390/s18051657. ISSN 1424-8220. PMC 5982167. PMID 29789447.
49. Zhang, Xiatian; Moubayed, Noura Al; Shum, Hubert P. H. (2022). "Towards Graph Representation Learning Based Surgical Workflow Anticipation". 2022 IEEE-EMBS International Conference on Biomedical and Health Informatics (BHI). IEEE. pp. 01–04. arXiv:2208.03824. doi:10.1109/BHI56158.2022.9926801. ISBN 978-1-6654-8791-7.
50. Jie Yin, Xiaoyong Chai and Qiang Yang, "High-level Goal Recognition in a Wireless LAN". In Proceedings of the Nineteenth National Conference on Artificial Intelligence (AAAI-04), San Jose, CA USA, July 2004. Pages 578–584.
51. Xiaoyong Chai and Qiang Yang, "Multiple-Goal Recognition From Low-level Signals". Proceedings of the Twentieth National Conference on Artificial Intelligence (AAAI 2005), Pittsburgh, PA USA, July 2005. Pages 3–8.
52. Derek Hao Hu, Qiang Yang. "CIGAR: Concurrent and Interleaving Goal and Activity Recognition", to appear in AAAI 2008.
53. Jie Yin, Dou Shen, Qiang Yang and Ze-nian Li. "Activity Recognition through Goal-Based Segmentation". Proceedings of the Twentieth National Conference on Artificial Intelligence (AAAI 2005), Pittsburgh, PA USA, July 2005. Pages 28–33.
54. D. Zhang, J. Ma, Q. Chen, and L. M. Ni. "An RF-based system for tracking transceiver-free objects". Proceedings of the Pervasive Computing and Communications. White Plains, USA, 2007: 135–144.
55. Q. Pu, S. Gupta, S. Gollakota, and S. Patel. “Whole-home gesture recognition using wireless signals”. Proceedings of the 19th Annual International Conference on Mobile Computing and Networking, New York, USA, 2013: 27–38.
56. D. Wu, D. Zhang, C. Xu, Y. Wang, and H. Wang. "Wider: Walking direction estimation using wireless signals". Proceedings of the 2016 ACM International Joint Conference on Pervasive and Ubiquitous Computing, New York, USA, 2016: 351–362.
57. H. Wang, D. Zhang, J. Ma, Y. Wang, Y. Wang, D. Wu, T. Gu, and B. Xie. "Human respiration detection with commodity wifi devices: Do user location and body orientation matter?". Proceedings of the 2016 ACM International Joint Conference on Pervasive and Ubiquitous Computing, New York, USA, 2016: 25–36.
58. "UCF101 – Action Recognition Data Set". 2021. Archived from the original on 2020-01-23.
59. "Papers with Code – HMDB51 Dataset". paperswithcode.com. Retrieved 2021-08-23.
60. Kay, Will; Carreira, Joao; Simonyan, Karen; Zhang, Brian; Hillier, Chloe; Vijayanarasimhan, Sudheendra; Viola, Fabio; Green, Tim; Back, Trevor; Natsev, Paul; Suleyman, Mustafa (2017-05-19). "The Kinetics Human Action Video Dataset". arXiv:1705.06950 [cs.CV].
61. Pollack, M.E., and et al., L. E. B. 2003. "Autominder: an intelligent cognitive orthotic system for people with memory impairment". *Robotics and Autonomous Systems* 44(3–4):273–282.
62. Gao, Lianli, et al. "A Web-based semantic tagging and activity recognition system for species' accelerometry data." *Ecological Informatics* 13 (2013): 47–56.
63. Nguyen, Tuan Anh, and Marco Aiello. "Energy intelligent buildings based on user activity: A survey." *Energy and buildings* 56 (2013): 244–257.
