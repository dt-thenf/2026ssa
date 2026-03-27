# Technical Evolution and Strategic Paradigms of Human Activity Recognition and Monitoring Systems

The field of Human Activity Recognition (HAR) has undergone a profound transformation over the last decade, evolving from a niche area of ubiquitous computing into a cornerstone of modern healthcare, industrial safety, and personalized sports analytics. Driven by the proliferation of wearable devices, advancements in deep learning, and the increasing demand for context-aware intelligent environments, Human Activity Recognition and Monitoring Systems (ARMS) are now fundamental to the development of autonomous, human-centric artificial intelligence.[1, 2, 3] As of 2024, the fitness-focused segment of wearable technology alone was valued at approximately USD 14.59 billion, with projections indicating a surge to USD 36.95 billion by 2032.[3] This economic trajectory reflects a broader technical shift toward systems that are not only capable of identifying basic movements such as walking or sitting but are also increasingly proficient at interpreting complex, composite, and heterogeneous activities in real-time.[3, 4, 5]

The core objective of any HAR system is the automated identification and interpretation of human actions based on data captured from a diverse array of sensors.[1, 2, 6] This process is inherently multi-disciplinary, necessitating expertise in signal processing for sensor data, computer vision for video streams, and sophisticated machine learning for classification.[2, 6, 7] Recent research from 2014 to 2025 highlights a critical transition from centralized, cloud-reliant architectures toward decentralized, edge-based paradigms that prioritize low latency, energy efficiency, and user privacy.[4, 8]

## Taxonomy of Sensing Modalities and Hardware Architectures

The architectural design of an ARMS is primarily dictated by its sensing modality, which determines the nature of the input data and the subsequent computational pipeline.[2, 9, 10] Contemporary systems are broadly categorized into three dominant paradigms: sensor-based, vision-based, and ambient-sensor-based techniques.[10, 11, 12]

### Wearable and Kinematic Sensing via Inertial Measurement Units

Inertial Measurement Units (IMUs) represent the most pervasive hardware components in the HAR landscape due to their integration into smartphones, smartwatches, and specialized fitness trackers.[3, 13] A standard IMU typically comprises a 3-axis accelerometer and a 3-axis gyroscope, with higher-end units often including a 3-axis magnetometer to provide 9 Degrees of Freedom (9-DoF).[1, 3, 14]

The accelerometer measures linear acceleration (m/s²) along three orthogonal axes, allowing the system to detect movement intensity and orientation relative to gravity.[1, 15, 16] The gyroscope captures angular velocity (rad/s), which is essential for determining the rotational dynamics of the body, such as the tilt of the torso or the swing of an arm.[1, 15] In specialized applications like smart insoles, these sensors are used to recognize not only ambulation—such as walking or running—but also detailed fitness activities like using a spinning bike, achieving accuracies as high as 98.56%.[17]

The placement of wearable sensors is a critical factor in recognition precision. Research indicates that sensors mounted on the waist or thigh are optimal for gait analysis, while wrist-mounted sensors are better suited for activities of daily living (ADLs) that involve significant hand movement.[18, 19, 20] Advanced systems like WatchHAR optimize this by operating entirely on smartwatches, using both IMU and audio data to classify over 25 activity classes with a latency as low as 11.8 ms.[18]

### Vision-Based Monitoring and RGB-D Paradigms

Vision-based HAR utilizes optical sensors to capture human motion. While traditional RGB cameras provide high-level visual information, they are susceptible to challenges such as variable lighting, background clutter, and privacy concerns.[1, 11, 19] To mitigate these issues, RGB-D sensors, such as the Microsoft Kinect, integrate infrared depth-finding cameras with standard RGB cameras.[19, 21] This allows the system to generate 3D skeleton tracking data, which abstracts human movement into a graph of joint coordinates.[2, 21, 22]

Skeleton-based action recognition has gained significant traction because it remains robust against changes in clothing or lighting.[2] By processing the temporal evolution of joint positions, models like Graph Convolutional Networks (GCNs) can identify complex interactions and gestures.[7, 22] However, vision systems are inherently limited by occlusion—where the line of sight between the camera and the subject is blocked—and the significant computational resources required for real-time video processing.[1, 11, 19]

### Ambient and Device-Free Sensing Environments

Ambient Sensor-Based Human Activity Recognition (AHAR) involves embedding sensors within the environment rather than on the user's person.[11] This paradigm is particularly effective for Ambient Assisted Living (AAL) and elderly care, as it does not rely on user compliance in wearing devices.[11, 23] Common ambient sensors include Passive Infrared (PIR) motion detectors, magnetic contact switches on doors and cabinets, pressure mats, and ultrasonic sensors.[11, 23, 24]

Device-free approaches leverage Radio Frequency (RF) signals, such as Wi-Fi Channel State Information (CSI) or ultrasonic waves, to detect movement.[9, 25] Ultrasonic sensors emit chirps typically between 23 kHz and 40 kHz.[26] When these sound waves bounce off a moving human, the returning signal exhibits a Doppler shift, providing a unique signature for different types of movement.[25] Ultrasonic systems are advantageous in environments like hallways, where they can detect a person's presence even around corners through secondary reflections.[25]

| Sensing Category | Typical Hardware Components | Key Advantages | Primary Constraints |
|---|---|---|---|
| Wearable | IMU (Accel, Gyro, Mag), Heart Rate Monitor | Precise motion capture, portable, 24/7 monitoring | User compliance, battery life, sensor drift |
| Vision-Based | RGB Camera, RGB-D (Kinect), Thermal Imaging | High spatial detail, multi-person tracking | Privacy concerns, lighting, occlusion |
| Ambient | PIR, Pressure Mats, Contact Switches | Unobtrusive, low cost, high privacy | Sparse data, requires infrastructure |
| RF/Acoustic | Wi-Fi CSI, Ultrasonic, Radar | Non-contact, works in dark, privacy-preserving | Complex signal processing, environmental noise |
| Physiological | ECG, EMG, PPG, EEG | Direct health insights, stress detection | Invasive, sensitive to motion artifacts |

## Computational Pipeline and Signal Processing Mechanics

The transformation of raw sensor signals into recognized activity labels follows a rigorous pipeline: data acquisition, preprocessing, segmentation, feature extraction, and classification.[5, 11, 27]

### Signal Preprocessing and Noise Reduction

Raw sensor data is often corrupted by noise from sensor vibrations, electronic interference, or gravitational components.[1, 5] Preprocessing techniques such as the application of low-pass filters are used to separate the body acceleration component from the gravitational acceleration.[1, 5, 16] In systems like DeepHAR, signal down-sampling is performed by averaging contiguous samples to denoise the data and reduce the computational burden on downstream models.[17]

### Windowing and Data Segmentation

Since activities are temporal in nature, continuous sensor streams must be segmented into discrete time windows.[4, 28] The sliding window approach is the most common, where data is partitioned into windows of fixed duration, such as 1 or 2 seconds.[4, 17, 18] To ensure that activity transitions are captured and to increase the effective size of training datasets, a 50% overlap between consecutive windows is frequently employed.[17, 28] The selection of the window size involves a trade-off between recognition latency and the ability of the model to capture the full temporal context of an action.[18, 29]

### Handcrafted Feature Engineering

Before the widespread adoption of deep learning, HAR relied heavily on handcrafted features extracted from the time and frequency domains.[13, 16, 19]

Time-Domain Features provide statistical insights into the signal's behavior over a window.[16, 19] Essential metrics include:

- Mean (M) and Standard Deviation (σ): Basic measures of signal magnitude and variability.[16]
- Signal Magnitude Area (SMA): A robust measure for identifying energy expenditure, calculated as the sum of the integrals of the magnitudes of the acceleration signals along the three axes.[16, 19]
- Jerk: The rate of change of acceleration, which helps in identifying sudden, sharp movements.[16]
- Zero-Crossing Rate: The number of times the signal crosses its mean value, often used to distinguish between different rhythmic activities.[19]

Frequency-Domain Features are derived by applying a Discrete Fourier Transform (DFT) to the time-series data.[19]

- Power Spectral Density (PSD): This feature captures the distribution of power across different frequencies, making it ideal for identifying periodic activities like walking or cycling.[19]
- Spectral Entropy: A measure of the complexity of the movement, helping to differentiate between activities that might have similar power levels but different patterns.[16, 19]

The mathematical formulation for the PSD in a window of N samples is given by:

```text
PSD(f)= | (1/N) * Σ(n=0 to N−1) x_n * e^(−j(2π/N)nf) |^2
```

where `x_n` represents the discrete signal samples.[19]

## Deep Learning Architectures for Advanced Activity Recognition

The field has largely transitioned from traditional machine learning models (like SVM, Random Forest, and k-NN) to deep learning architectures that automatically learn hierarchical representations from raw data.[1, 7, 19]

### Convolutional and Recurrent Paradigms

Convolutional Neural Networks (CNNs) are particularly effective at extracting spatial features from multi-channel sensor data.[1, 5, 30] By treating a window of sensor readings as a 1D or 2D image, CNNs can learn to detect local motifs—such as the specific oscillation of an ankle during a step—regardless of where they occur in the window.[5, 30]

Recurrent Neural Networks (RNNs), specifically Long Short-Term Memory (LSTM) units, are designed to handle sequential dependencies.[29, 30] LSTMs utilize memory cells and gating mechanisms to retain information over long time intervals, which is crucial for recognizing complex, multi-stage activities such as "preparing a meal" or "performing a sequence of exercises".[7, 29, 30] Hybrid architectures, often referred to as DeepConvLSTM, combine the spatial feature extraction of CNNs with the temporal modeling capabilities of LSTMs to achieve state-of-the-art performance across diverse datasets.[5, 7, 27]

### Transformers and Self-Attention Mechanisms

Recently, Transformer architectures have begun to replace RNNs in many HAR tasks.[1, 7] Unlike RNNs, which process data sequentially, Transformers use self-attention mechanisms to weigh the importance of different time steps within a window simultaneously.[1, 2] This allows the model to capture global context and long-range dependencies more effectively, leading to improved recognition of subtle and fine-grained activities.[1, 7]

### Open-Vocabulary and LLM-Integrated Recognition

A significant limitation of traditional HAR models is their restriction to a predefined set of activity classes present in the training data.[31] The emergence of Open-Vocabulary Human Activity Recognition (OV-HAR) addresses this by framing activity recognition as a text generation problem.[31] By translating sensor data into semantically meaningful embeddings, these systems can identify unseen activities by comparing them to natural language descriptions using pre-trained Large Language Models (LLMs).[31] For instance, a movement sequence can be described as "arm extension followed by horizontal hand motion," which the system then maps to the label "swiping left".[31]

## Multi-Modal Fusion and Context-Aware Integration

Modern ARMS frequently integrate data from multiple modalities to enhance robustness and accuracy, a process known as multimodal data fusion.[2, 32, 33]

### Fusion Strategies: Early, Late, and Hybrid

The stage at which data from different sources are combined is a critical design choice.[32, 33, 34]

- **Early Fusion (Feature-Level):** Features are extracted from each modality (e.g., RGB video and IMU data) and concatenated into a single high-dimensional vector before being passed to a classifier.[2, 32, 34] This allows the model to learn joint representations and capture cross-modal correlations, but it requires highly synchronized data and can be computationally intensive.[2, 33, 34]
- **Late Fusion (Decision-Level):** Each modality is processed by an independent model, and the individual predictions are combined at the final stage using techniques like voting or weighted averaging.[2, 33, 34] This approach is robust to missing data and allows for the use of specialized architectures for each sensor type, but it may fail to capture complex interactions between sensors.[2, 33, 35]
- **Hybrid/Intermediate Fusion:** This method integrates features at multiple intermediate layers of the neural network.[2, 33] Modern hybrid systems often use cross-attention mechanisms, where one modality (e.g., text descriptions) guides the feature extraction in another modality (e.g., skeleton joints) to improve fine-grained discrimination.[2, 33, 36]

| Fusion Strategy | Integration Point | Key Strength | Major Weakness |
|---|---|---|---|
| Early Fusion | Feature extraction stage | Captures low-level cross-modal correlations | Sensitive to temporal misalignment |
| Late Fusion | Decision/Output stage | Robust to sensor failure or noise | Loses deep inter-modality dependencies |
| Intermediate | Hidden layers of the network | Balances joint learning with modality-specific traits | High architectural complexity |
| Attention-Based | Cross-attention modules | Dynamically weighs the most relevant sensor | Demands significant memory and compute |

### The Role of Contextual Information

The accuracy of HAR systems can be significantly improved by integrating contextual information, which provides semantic grounding for activities.[37] Context can be categorized into three groups:

- **Sensor Context:** Position data of the subject or objects being handled (e.g., using BLE for indoor localization).[37]
- **Process Context:** High-level state information, such as current location or tool usage, which helps distinguish between visually similar activities (e.g., "washing hands" in a kitchen vs. "washing hands" in a bathroom).[37]
- **Knowledge Context:** Prior knowledge about the ideal flow of a process or the composition of an order in industrial logistics.[37]

## Edge AI and TinyML for Real-Time On-Device Inference

One of the most significant shifts in HAR is the transition from cloud-based processing to Edge AI and TinyML.[4, 38] Processing data directly at the point of capture offers several critical advantages:

### Latency, Connectivity, and Autonomy

Cloud-based systems rely on continuous internet connectivity and can suffer from significant latency due to round-trip data transmission.[4] Edge-based systems enable real-time responses, which is essential for time-critical applications like fall detection or industrial collision avoidance.[4, 38] Furthermore, edge devices can operate autonomously in environments with restricted connectivity, such as remote industrial sites or deep-sea operations.[4, 18]

### Energy Efficiency and Battery Life

Transmitting large volumes of high-frequency sensor data is the most energy-intensive operation for wearable devices.[4] By performing inference locally and only transmitting high-level activity labels, edge devices can significantly extend their battery life.[4, 18]

### Implementation via TensorFlow Lite / LiteRT

The deployment of deep learning models on resource-constrained microcontrollers is made possible by frameworks like LiteRT.[4] The workflow typically involves training a model in a high-level environment like TensorFlow/Keras, followed by quantization and compression to reduce the model's memory footprint without a substantial loss in accuracy.[4] Proof-of-concept systems have demonstrated that models for walking, jumping, and standing can run efficiently on hardware as small as an Arduino Nano 33 BLE.[4]

## Privacy, Security, and Decentralized Learning Paradigms

As HAR systems become more pervasive, protecting the sensitive motion and physiological data of users has become a paramount concern.[3, 8, 39]

### Federated Learning (FL) and Privacy Preservation

Federated Learning allows for the collaborative training of models without the need to centralize raw user data.[8, 15, 40] In an FL framework, training occurs locally on the user's device (e.g., a smartphone or smartwatch). Only the resulting model updates—such as weights or gradients—are sent to a central server to be aggregated into a global model.[8, 15] This approach inherently preserves privacy and is particularly suited for healthcare applications where data sensitivity is high.[8, 40]

### Self-Supervised Learning (SSL) and Data Scarcity

The reliance on large labeled datasets is a major bottleneck for HAR development.[40] Self-Supervised Learning addresses this by learning representations from unlabeled data.[40, 41] Techniques like Contrastive Predictive Coding (CPC) capture the temporal structure of sensor data streams, allowing models to be pre-trained on massive unlabeled datasets (like the 700,000 person-days of accelerometer data from the UK Biobank).[40] These pre-trained models can then be fine-tuned with as few as five labeled samples per class to achieve high performance on specific tasks.[40]

### Real-Time Redaction in Vision Systems

For vision-based monitoring, real-time redaction systems like PrivacyGuard use deep learning to identify and obscure sensitive information—specifically human faces and license plates—directly at the edge.[42] By utilizing high-speed detectors like YOLOv8-L, these systems can apply Gaussian blur or pixelation to sensitive regions in video frames with a latency of less than 40ms, ensuring that privacy is maintained even in live streaming or CCTV applications.[42]

The technical specifications of such a system highlight the balance between speed and accuracy:

| Parameter | Specification |
|---|---|
| Base Model | YOLOv8-L (Unified Detector) |
| Input Resolution | 640 x 640 pixels |
| Inference Speed | 25 FPS (RTX 5090) |
| Detection Accuracy | 0.836 mIoU |
| Redaction Filter | Gaussian Blur (k=25,σ=7) |
| Model Size | 53.2 Million Parameters |

## Commercial Landscape and Sector-Specific Applications

ARMS technology has moved beyond research labs into large-scale commercial deployments across healthcare, sports, and industrial sectors.[23, 43, 44]

### Healthcare and Remote Patient Monitoring

In the medical domain, HAR is a critical component of Remote Patient Monitoring (RPM) systems.[45, 46, 47] Platforms like Murphi.ai and Medtronic utilize AI to detect subtle changes in movement patterns that may indicate health deterioration, sometimes up to 72 hours before a crisis.[45, 46] For seniors, smart home systems incorporate fall detection, medication adherence monitoring, and vital sign tracking through non-invasive sensors.[48, 49]

### Sports Analytics and Elite Performance

The sports sector leverages high-precision wearables to optimize athlete performance and reduce injury risks.[43, 50, 51] Devices like the Garmin Forerunner 955 and WHOOP Strap 4.0 provide detailed analysis of recovery, strain, and movement technique.[43, 50] Innovative solutions include smart insoles (Adidas GMR) and connected basketballs (Wilson X) that track on-field performance and skill development.[50] Advanced head-mounted displays (FORM Smart Swim 2) even project real-time metrics onto goggles to provide feedback without disrupting the athlete's rhythm.[51]

### Industrial Safety and Ergonomics

Industrial "Smart PPE" focuses on reducing workplace accidents and preventing musculoskeletal disorders (MSDs).[44, 52, 53] Wearable sensors embedded in vests, helmets, and belts monitor for hazardous motions, heavy load handling, and improper posture.[44, 52] Systems like MākuSafe capture environmental data and motion patterns to provide safety leaders with risk intelligence, helping to mitigate hazards before they result in injuries.[54]

| Sector | Primary Objective | Leading Technologies |
|---|---|---|
| Healthcare | Chronic disease management, elderly care | RPM platforms, fall detection, smart medication hubs |
| Sports | Performance optimization, injury prevention | 9-DoF IMUs, dual-frequency GPS, neural wristbands |
| Industrial | Worker safety, OSH compliance | Smart helmets, haptic vests, posture-correcting belts |
| Smart Home | AAL, security, energy management | Ambient PIR, RF sensing, acoustic monitors |

## Ethical Frameworks and the Surveillance Paradox

The deployment of ARMS technology presents significant ethical challenges that must be addressed through transparent policy and robust consent frameworks.[39, 55, 56]

### Autonomy and Informed Consent

The passive and pervasive nature of activity monitoring often blurs the lines of consent.[39, 56] Ethical systems must prioritize informed, voluntary, and revocable consent, ensuring that users fully understand what data is being collected and how it will be used.[39, 55] This is particularly complex in employment settings, where continued employment might imply a level of "implied consent" that can lead to ethical dilemmas.[55, 56]

### The Surveillance Paradox and Trust

Over-surveillance can lead to the "Surveillance Paradox," where excessive monitoring erodes trust and causes employees or residents to focus on compliance rather than genuine engagement.[55] To mitigate this, monitoring should focus on aggregate analytics—such as heatmaps of workspace utilization—rather than individual-level behavioral tracking, wherever possible.[55]

### Accountability and Algorithmic Bias

Developers and manufacturers are increasingly accountable for ensuring that their algorithms are free from bias.[39, 56] Since HAR data often primarily comes from specific demographics, models can inadvertently discriminate against underrepresented groups.[39] Robust ethical frameworks must include bias mitigation techniques, annual consent renewals, and digital dashboards that allow users to manage their own data and privacy preferences.[39, 55]

## Open-Source Ecosystem and Research Standards

The advancement of HAR is underpinned by a growing ecosystem of open-source datasets and software toolboxes designed to unify the fragmented research landscape.[20, 57, 58]

### Standardization via OpenHAR and WHAR

One of the most pressing challenges in the field is the absence of a standardized data format, which complicates the reuse of datasets and hinders reproducibility.[57] Frameworks like OpenHAR (a Matlab-based toolbox) and WHAR (a Python-based library) aim to solve this by providing unified access to disparate datasets.[20, 57, 58] These tools homogenize units, sampling rates, and body position IDs across multiple studies, allowing for more robust benchmarking of new algorithms.[20, 58]

### Benchmark Datasets for Research

A variety of publicly available datasets serve as the training and testing ground for modern HAR systems:

- UCI-HAR: Smartphone sensor data from 30 subjects performing 6 daily activities.[2, 57, 59]
- Opportunity: A high-dimensional dataset featuring body-worn, object, and ambient sensors for benchmarking multimodal fusion.[57, 60]
- PAMAP2: A widely used dataset for physical activity monitoring including heart rate and IMU data.[28, 57]
- NTU RGB+D: A massive scale dataset for 3D skeleton-based action recognition.[2, 22]

## Strategic Outlook and Future Directions

The next phase of evolution in Human Activity Recognition will likely be characterized by the integration of foundation models and the expansion into the far edge of computing.[3, 40, 49]

### Foundation Models and Generative AI

The success of self-supervised pre-training on massive datasets like the UK Biobank suggests that HAR is moving toward "foundation models" for human motion.[40] These models will likely be capable of zero-shot transfer to new activities and users, dramatically reducing the need for localized labeling.[40] Furthermore, Generative AI will increasingly be used for data augmentation, creating synthetic sensor streams to train models on rare but critical events, such as specific medical emergencies or hazardous industrial accidents.[3, 10]

### Federated Continual Learning

Future systems will move beyond static models toward federated continual learning ecosystems.[3, 8, 61] These systems will not only preserve privacy by keeping data local but will also continuously adapt to changes in a user’s physical condition or environment over time.[3, 61] This "lifelong learning" capability will be essential for health monitoring in aging populations, where movement patterns naturally shift over decades.[3, 58]

Through the synthesis of hardware innovation, deep representation learning, and decentralized privacy frameworks, Activity Recognition and Monitoring Systems are poised to become an invisible but indispensable layer of the modern digital world, providing the contextual intelligence required for truly autonomous and human-centered technology.

---

## References

- Advancements in Human Activity Recognition: A Comprehensive ..., https://www.researchgate.net/publication/391648375_Advancements_in_Human_Activity_Recognition_A_Comprehensive_Survey_of_Sensor-Based_and_Vision-Based_Approaches
- A Comprehensive Methodological Survey of Human Activity ... - MDPI, https://www.mdpi.com/1424-8220/25/13/4028
- Towards Generalizable Human Activity Recognition: A Survey - arXiv, https://arxiv.org/html/2508.12213v1
- Human Activity Recognition on Embedded Devices: An ... - SciTePress, https://www.scitepress.org/Papers/2025/134753/134753.pdf
- Deep-HAR: an ensemble deep learning model for recognizing the simple, complex, and heterogeneous human activities - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC9946874/
- Human Action Recognition: A Taxonomy-Based Survey, Updates, and Opportunities - MDPI, https://www.mdpi.com/1424-8220/23/4/2182
- Machine Learning for Human Activity Recognition: State-of-the-Art Techniques and Emerging Trends - MDPI, https://www.mdpi.com/2313-433X/11/3/91
- Federated Learning for Human Activity Recognition: Overview, Advances, and Challenges, https://nchr.elsevierpure.com/en/publications/federated-learning-for-human-activity-recognition-overview-advanc/
- The State-of-the-Art Sensing Techniques in Human Activity Recognition: A Survey - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC9229953/
- Machine Learning Techniques for Sensor-Based Human Activity Recognition with Data Heterogeneity—A Review - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC11679906/
- Deep Learning-Based Human Activity Recognition Using Binary Ambient Sensors - MDPI, https://www.mdpi.com/2079-9292/15/2/428
- CMES | Free Full-Text | Deep Learning and Federated Learning in Human Activity Recognition with Sensor Data: A Comprehensive Review - Tech Science Press, https://www.techscience.com/CMES/v145n2/64573/html
- Human Activity Recognition, Monitoring, and Analysis Facilitated by Novel and Widespread Applications of Sensors - ResearchGate, https://www.researchgate.net/publication/383117809_Human_Activity_Recognition_Monitoring_and_Analysis_Facilitated_by_Novel_and_Widespread_Applications_of_Sensors
- Sensors Products Category on Adafruit Industries, https://www.adafruit.com/category/35
- Federated weakly-supervised representation learning for privacy ..., https://ijsra.net/sites/default/files/fulltext_pdf/IJSRA-2025-3076.pdf
- Feature Engineering for Human Activity Recognition - The Science and Information (SAI) Organization, https://thesai.org/Downloads/Volume12No2/Paper_21-Feature_Engineering_for_Human_Activity_Recognition.pdf
- DeepHAR: a deep feed-forward neural network algorithm for smart insole-based human activity recognition - ResearchGate, https://www.researchgate.net/publication/369265932_DeepHAR_a_deep_feed-forward_neural_network_algorithm_for_smart_insole-based_human_activity_recognition
- WatchHAR: Real-time On-device Human Activity Recognition System for Smartwatches, https://arxiv.org/html/2509.04736v1
- Physical Human Activity Recognition Using Wearable Sensors - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC4721778/
- OpenHAR: A Matlab Toolbox for Easy Access to Publicly Open Human Activity Data Sets—Introduction and Experimental Results | Request PDF - ResearchGate, https://www.researchgate.net/publication/335710035_OpenHAR_A_Matlab_Toolbox_for_Easy_Access_to_Publicly_Open_Human_Activity_Data_Sets-Introduction_and_Experimental_Results
- RGB-D Cameras and Brain–Computer Interfaces for Human Activity Recognition: An Overview - MDPI, https://www.mdpi.com/1424-8220/25/20/6286
- firework8/Awesome-Skeleton-based-Action-Recognition - GitHub, https://github.com/firework8/Awesome-Skeleton-based-Action-Recognition
- Hardware for Recognition of Human Activities: A Review of Smart Home and AAL Related Technologies - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC7435866/
- How Do Ultrasonic Sensors Work? | Senix News, https://senix.com/newsroom/?p=how-do-ultrasonic-sensors-work
- Ultrasonic Methods for Human Motion Detection - NATO, https://publications.sto.nato.int/publications/STO%20Meeting%20Proceedings/RTO-MP-SET-107/MP-SET-107-09.pdf
- The Basics of Ultrasonic Sensors - Same Sky, https://www.sameskydevices.com/blog/the-basics-of-ultrasonic-sensors
- TCN-attention-HAR: human activity recognition based on attention mechanism time convolutional network - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC10978978/
- Deep-Learning-for-Human-Activity-Recognition/README.md at master - GitHub, https://github.com/Koutoulakis/Deep-Learning-for-Human-Activity-Recognition/blob/master/README.md
- Human Activity Recognition (HAR): Fundamentals, Models, Datasets - V7 Labs, https://www.v7labs.com/blog/human-activity-recognition
- Sensor-Based Human Activity Recognition with Spatio-Temporal Deep Learning - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC8003187/
- Initial Findings on Sensor based Open Vocabulary Activity Recognition via Text Embedding Inversion - arXiv, https://arxiv.org/pdf/2501.07408
- (PDF) Multimodal Data Fusion Techniques - ResearchGate, https://www.researchgate.net/publication/383887675_Multimodal_Data_Fusion_Techniques
- Multimodal Data Fusion: Key Techniques, Challenges & Solutions - Sapien, https://www.sapien.io/blog/mastering-multimodal-data-fusion
- Early Fusion vs. Late Fusion in Multimodal Data Processing - GeeksforGeeks, https://www.geeksforgeeks.org/deep-learning/early-fusion-vs-late-fusion-in-multimodal-data-processing/
- Multimodal Models and Fusion - A Complete Guide - Medium, https://medium.com/@raj.pulapakura/multimodal-models-and-fusion-a-complete-guide-225ca91f6861
- Lightweight Multi-Scale Framework for Human Pose and Action Classification - MDPI, https://www.mdpi.com/1424-8220/26/4/1102
- Sensor-Based Human Activity Recognition - MDPI, https://mdpi-res.com/bookfiles/book/12455/SensorBased_Human_Activity_Recognition.pdf?v=1773414086
- Smarter Safety at Work: AI Vision-Based Solutions for Preventing Musculoskeletal Disorders (MSDs) - e-con Systems, https://www.e-consystems.com/blog/camera/applications/smarter-safety-at-work-ai-vision-based-solutions-for-preventing-musculoskeletal-disorders-msds/
- Privacy, ethics, transparency, and accountability in AI systems for wearable devices - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC12209263/
- Self-Supervised Federated Learning for Personalized Human ..., https://www.researchgate.net/publication/384486525_Self-Supervised_Federated_Learning_for_Personalized_Human_Activity_Recognition
- SelfVis: Self-Supervised Learning for Human Activity Recognition Based on Area Charts, https://www.computer.org/csdl/journal/ec/2025/01/10520168/1WDYsyAJyog
- PrivacyGuard: Real-Time Detection and Redaction of ... - CS231n, https://cs231n.stanford.edu/2025/papers/text_file_840595592-cs231n_final_report.pdf
- Wearable Technology in Sports: The Best Fitness Trackers - PREMIUM Medical Circle, https://premiummedicalcircle.com/en/artikel/wearable-technology-in-sports-2025-the-best-fitness-trackers-for-your-health
- Smart wearables for workplace safety - RoSPA, https://www.rospa.com/health-and-safety-news/smart-wearables-for-workplace-safety
- Top Healthcare Remote Patient Monitoring Companies In 2025 - Murphi AI, https://murphi.ai/top-remote-patient-monitoring-companies-leading-healthcare-in-2025/
- World's Top 50 Companies in Patient Monitoring Devices in 2025 - Spherical Insights, https://www.sphericalinsights.com/blogs/world-s-top-50-companies-in-patient-monitoring-devices-in-2025-watch-list-statistics-report-2024-2035
- 2025 Best In KLAS Remote Patient Monitoring - KLAS Research, https://klasresearch.com/best-in-klas-ranking/remote-patient-monitoring/2025/338
- Top Smart Home Medical Devices for Seniors in 2025-2026, https://allseniors.org/articles/top-smart-home-medical-devices-for-seniors-in-2025-2026/
- Ten Health and Aging Tech offerings from CES 2025, https://www.ageinplacetech.com/blog/ten-health-and-aging-tech-offerings-ces-2025
- The Best Devices for Tracking Movements in 2024 - Sency.ai, https://www.sency.ai/post/best-devices-tracking-movement-2024
- Wearable Devices Technology in Sport Market - Companies & Trends - Mordor Intelligence, https://www.mordorintelligence.com/industry-reports/wearable-devices-in-sports-market
- Industrial safety wearables, https://elitacwearables.com/industrial-safety-wearables/
- Utilizing Safety Wearables in the Workplace - KORE Wireless, https://www.korewireless.com/blog/utilizing-safety-wearables-in-the-workplace/
- Wearable Safety Tech For Innovative Captive Strategies Members | MākuSafe, https://makusafe.com/ics/
- Ethical issues with employee monitoring: Best practices and compliance - MiHCM, https://mihcm.com/resources/blog/ethical-issues-with-employee-monitoring-best-practices-and-compliance/
- Wearable Sensors: An Ethical Framework for Decision-Making | NIOSH Science Bulletin, https://www.cdc.gov/niosh/bulletin/2017/sensors.html
- WHAR Datasets: An Open Source Library for Wearable Human Activity Recognition, https://arxiv.org/html/2508.16604v1
- OpenHAR: A Matlab Toolbox for Easy Access to Publicly Open Human Activity Data Sets, https://www.semanticscholar.org/paper/OpenHAR%3A-A-Matlab-Toolbox-for-Easy-Access-to-Open-Siirtola-Koskim%C3%A4ki/dc9cfabae22ac217731c5f75d59576b5c18e7cde
- Human Activity Recognition Using Smartphones - UCI Machine Learning Repository, https://archive.ics.uci.edu/ml/datasets/human+activity+recognition+using+smartphones
- OPPORTUNITY Activity Recognition - UCI Machine Learning Repository, https://archive.ics.uci.edu/dataset/226/opportunity+activity+recognition
- FedOpenHAR: Federated Multitask Transfer Learning for Sensor-Based Human Activity Recognition - ResearchGate, https://www.researchgate.net/publication/391058871_FedOpenHAR_Federated_Multitask_Transfer_Learning_for_Sensor-Based_Human_Activity_Recognition
