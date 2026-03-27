# Advanced Paradigms in Real-Time Human Activity Recognition and Monitoring Systems

The discipline of Human Activity Recognition (HAR) has ascended to a position of central importance in the landscape of ubiquitous computing, serving as the foundational mechanism for seamless human-robot collaboration (HRC), proactive healthcare monitoring, and intelligent industrial safety.[1, 2, 3] At its core, HAR involves the automated identification and interpretation of human physical movements through a sophisticated pipeline of sensing modalities and learning algorithms.[4] The field has evolved from simple gesture recognition into a complex multi-disciplinary endeavor that integrates computer vision, signal processing, and machine learning to perceive, predict, and respond to human actions in unconstrained environments.[3, 4, 5] Achieving a seamless interaction between humans and autonomous systems requires a nuanced understanding of motion-driven interactions and contact-force dynamics, often where movement and force are inextricably interconnected.[1]

## Sensing Modalities and the Physical Infrastructure of Recognition

The architectural integrity of a real-time HAR system begins with the selection of sensing modalities, which are generally categorized into vision-based (external) and sensor-based (wearable or ambient) systems.[1, 6] Vision-based approaches leverage optical technologies such as RGB cameras, depth sensors, or motion capture systems to monitor joint movements and extract environmental context.[1, 4] While RGB cameras provide rich texture information similar to human vision, they are notoriously sensitive to lighting conditions, viewpoint variations, and occlusions.[4, 6] Depth sensors, including LiDAR and Kinect-style infrared sensors, offer a robust alternative by providing 3D spatial information that remains invariant to ambient illumination, thus facilitating effective foreground-background segmentation even in total darkness.[4]

Wearable solutions provide a different perspective by tracking motion directly from the body's frame of reference. Inertial Measurement Units (IMUs), comprising accelerometers and gyroscopes, are frequently embedded in smartphones, watches, or dedicated data gloves to estimate spatial orientation and joint angles.[1, 7] Although IMUs are ideal for capturing high-frequency movements in joints with multiple degrees of freedom, they suffer from cumulative error (drift) and challenges in sensor-to-body alignment.[1] Flex sensors, which rely on mechanical deformation, offer a low-cost method for tracking joint flexion but are prone to long-term wear and struggle with multi-axial joint estimation.[1]

Tactile sensing adds another dimension of intelligence, particularly in scenarios involving physical human-robot interaction. Conventional tactile sensors utilize resistive, capacitive, or piezoelectric technologies to measure contact forces at the fingertips or palms.[1] A more advanced approach involves vision-based tactile sensing, which utilizes a camera to analyze the deformation of a soft, compliant membrane under pressure.[1, 8] This distributed force sensing not only classifies the intensity of interaction but also enhances safety by providing a mechanical buffer during physical contact.[1]

| Sensing Modality | Data Characteristics | Environmental Sensitivity | Primary Limitation |
|---|---|---|---|
| RGB Video | 2D/3D Image Sequences | High (Lighting, Occlusion) | Privacy concerns [4, 6] |
| Depth Maps | 3D Point Clouds | Low (Light-invariant) | Limited indoor range [4] |
| IMU (Wearable) | 1D/3-Axial Time-series | Negligible | Cumulative drift [1, 7] |
| Tactile Sensor | Contact Force/Pressure | Negligible | Physical discomfort [1, 4] |
| Event Cameras | Pixel Intensity Changes | Low | High complexity [9] |

The emergence of non-contact, device-free sensing, such as radar and Wi-Fi Channel State Information (CSI), represents a significant shift toward unobtrusive monitoring. These systems utilize signal reflections to infer motion, effectively eliminating the need for users to wear devices or be captured on traditional video.[4, 10] This is particularly advantageous for elderly care or monitoring individuals with skin diseases who cannot tolerate wearable sensors.[10, 11]

## Algorithmic Foundations: Transitioning to Deep Representations

Historically, HAR relied on hand-crafted feature extraction, where researchers designed specific descriptors for body shape, silhouettes, or global motion patterns.[6] While effective in constrained environments, these traditional methods lacked the generalization required for real-world "in the wild" scenarios.[6] The maturation of deep learning has revolutionized the field by enabling the automatic learning of hierarchical features directly from raw sensor data.[7, 12] In this paradigm, initial layers learn primitive features like edges or signal motifs, while deeper layers aggregate these into sophisticated representations of complex activities.[12]

Real-time HAR is fundamentally a time-series classification challenge, as human actions are sequential and temporally dependent.[7] Deep models must therefore be capable of capturing both spatial and temporal dynamics. Recurrent Neural Networks (RNNs) and their variants, such as Long Short-Term Memory (LSTM) networks, are specifically designed to handle sequential data.[7, 13] LSTMs utilize a gating mechanism to regulate the flow of information, allowing the model to retain long-term dependencies of an action sequence while disregarding irrelevant noise.[7, 14]

Hybrid architectures often represent the state-of-the-art for multivariate time-series data. The CNN-LSTM model, for instance, employs a Convolutional Neural Network (CNN) as a front-end feature extractor to identify spatial patterns across various sensor axes (e.g., X, Y, and Z axes of an accelerometer).[7, 14] These features are then passed to an LSTM back-end to model the temporal evolution of the activity.[14] Benchmarks on the UCI HAR dataset indicate that such hybrid models can achieve accuracies exceeding 94%, significantly outperforming standalone models.[14]

## Spatio-Temporal Modeling and 3D Convolutional Networks

In the domain of vision-based recognition, capturing the "when" of an action is as critical as the "what." Traditional 2D CNNs process video frames as independent images, which can lead to a loss of temporal context. To address this, 3D Convolutional Neural Networks (3D-CNNs) extend the convolutional kernel into the temporal dimension, effectively processing a stack of frames as a 3D volume.[15, 16, 17]

The C3D architecture represents one of the earliest successful applications of this concept, demonstrating that 3D kernels can learn spatial and temporal features simultaneously.[15, 16] However, 3D convolutions significantly increase the parameter count, making models difficult to train and computationally expensive for edge deployment.[17] This led to the development of the "Two-Stream Inflated 3D ConvNet" (I3D), which "inflates" 2D filters from pre-trained image models into 3D filters, leveraging knowledge from massive image datasets while capturing motion.[15, 16, 18] Another prominent architecture, the SlowFast network, uses a dual-stream approach: a "Slow" pathway with a low frame rate to capture spatial semantics and a "Fast" pathway with a high frame rate to capture fine-grained motion patterns.[18]

| Model Variant | Strategy | Reported Performance | Use Case |
|---|---|---|---|
| C3D | 3D Spatial-Temporal Kernels | 83.2% Accuracy | Generic video classification [15] |
| I3D | Inflated 2D Pre-trained Filters | 88.1% Accuracy | Complex action recognition [16] |
| SlowFast | Multi-rate Dual Pathways | SOTA on Kinetics | High-speed motion analysis [18] |
| R3D/AR3D | Residual/Attention 3D Kernels | Improved Training | Resource-constrained video [17] |

Refinements such as Residual 3D Networks (R3D) and Attention Residual 3D Networks (AR3D) have been introduced to combat the exponential increase in parameters.[17] By decoupling the 3D convolution kernel and integrating attention mechanisms, these models can focus on the most relevant spatial and temporal regions, thereby reducing sensitivity to background clutter and improving recognition in cluttered environments.[17]

## Graph-Based Representations and Skeleton-Based Tracking

A significant advancement in privacy-preserving and computationally efficient HAR is the shift toward skeleton-based recognition. Rather than processing high-resolution video frames, these systems represent the human body as a graph where joints are nodes and bones are edges.[19, 20, 21] This abstraction naturally eliminates background noise and focuses entirely on the kinematic structure of the actor.[21, 22]

The Spatial-Temporal Graph Convolutional Network (ST-GCN) was a pioneering framework that modeled the human skeleton as a non-Euclidean graph, performing convolutions in both spatial (joint connectivity) and temporal (joint trajectory) domains.[19, 21] Recent research has focused on the limitations of fixed skeletal topologies, which cannot always capture the dynamic interactions required for fine-grained actions.[19]

State-of-the-art (SOTA) graph models for 2024 and 2025 have introduced adaptive and hierarchical learning strategies:

- **CTR-GCN (Channel-wise Topology Refinement):** This model learns feature-dependent adjacency matrices for each channel group, allowing for flexible correlations that transcend the physical anatomy.[19]
- **HD-GCN (Hierarchically Decomposed GCN):** This architecture decomposes the skeleton into a hierarchy of subgraphs, enabling the model to reason about local part dynamics (e.g., finger movement) alongside global body coordination.[19]
- **Hyper-GCN:** This approach constructs a hyper-graph where hyper-edges connect multiple nodes simultaneously. This enables the model to capture action-driven multi-vertex relations and implicit dependencies between non-adjacent joints.[20, 22]
- **SAT-GCN (Semantics-Assisted Training):** This network integrates text features from action labels into the training process, using contrastive loss to guide the skeleton encoder and improving accuracy with fewer parameters.[23]

The precision of skeleton-based systems is further enhanced by the inclusion of high-order geometric features. Modern multi-stream networks often integrate joint coordinates (first-order), bone lengths and angles (second-order), and temporal derivatives like velocity and acceleration to distinguish between similar actions like "sitting" and "standing".[23, 24, 25]

## Real-Time Deployment and Edge Computing Infrastructure

For a monitoring system to be effective, it must operate with minimal latency. In applications like autonomous vehicles or surgical assistance, even a few milliseconds of delay can have catastrophic consequences.[26, 27] The computational burden is increasingly shifted toward edge computing, where processing occurs locally on the device rather than in a distant cloud.[28, 29]

NVIDIA's Jetson series has become the industry standard for edge AI deployment. These modules utilize System-on-Module (SoC) architectures that combine multi-core ARM CPUs with high-performance GPUs and specialized Tensor Cores for accelerated deep learning inference.[30, 31, 32]

| Hardware Platform | Architecture | AI Performance | Primary Advantage |
|---|---|---|---|
| Jetson Nano | Maxwell | 0.5 TFLOPS | Entry-level cost/power [30] |
| Orin Nano | Ampere | 40 TOPS | Compact high-performance [30] |
| AGX Xavier | Volta | 32 TOPS | Proven industrial reliability [31] |
| AGX Orin | Ampere | 275 TOPS | Power-efficient multi-model [32] |
| Google Coral | TPU | 4 TOPS | Ultra-low power inference [31] |

The AGX Orin module, in particular, offers a 7.5x better performance-per-watt ratio for INT8 inference compared to desktop-class GPUs like the RTX 4090.[32] Optimization techniques such as quantization (converting FP32 weights to INT8 or FP16) and model pruning are essential for fitting large 3D-CNNs or GCNs onto these modules.[32, 33] The TensorRT SDK further accelerates this by optimizing the network's computation graph specifically for the Jetson hardware, often yielding a 2.4x latency improvement.[32, 34]

## Pipeline Optimization and Latency Mitigation

Achieving real-time performance on live video streams (e.g., 30 FPS) requires addressing bottlenecks across the entire computational stack.[35] Research into video-based HAR pipelines has identified optical flow extraction as a primary latency culprit. Traditional OpenCV implementations often struggle to maintain more than 3 FPS on embedded platforms.[35] The RT-HARE (Real-Time Human Action Recognition at the Edge) framework mitigates this by utilizing neural-network-based feature extraction and video down-sampling, successfully boosting performance to a consistent 30 FPS while maintaining high accuracy.[35]

Data pipeline orchestration is another critical factor. Systems must minimize "stall time"—the idle period where the GPU waits for the CPU to fetch or preprocess data.[26, 31] Using high-bandwidth memory (HBM), DMA (Direct Memory Access), and pinning threads to specific CPU cores can reduce context switching and improve cache locality.[36, 37] For wearable devices, the WatchHAR architecture unifies preprocessing and inference into an end-to-end module that approximates a mel-filter bank as a 1D convolution, achieving processing times of just 11.8 ms directly on a smartwatch.[2]

## Multimodal Fusion and Contextual Awareness

A single sensing modality often provides only a "partial truth" regarding a human's state.[38] Multimodal fusion integrates information from heterogeneous sources—such as RGB, depth, audio, and IMUs—to provide a more robust and semantically rich representation of an activity.[39, 40] Fusion strategies are generally classified by the stage at which data is combined:

- **Early Fusion (Data-Level):** Raw inputs are concatenated or merged prior to any significant processing. This allows the model to learn joint representations from the start but is highly sensitive to sensor misalignment and scaling issues.[39, 40]
- **Intermediate Fusion (Feature-Level):** Modalities are processed by independent encoders into latent embeddings, which are then fused using attention mechanisms or cross-modal operators. This is the most prevalent strategy in modern autonomous systems.[39, 41]
- **Late Fusion (Decision-Level):** Each modality branch makes an independent prediction, and the final result is determined through averaging, majority voting, or learned gating. This approach is highly modular and resilient to missing sensor data.[39, 40, 41]

The integration of motion and tactile data is particularly powerful in robotic collaboration. A multimodal system combining a vision-based tactile sensor with an IMU data glove consistently outperforms single-modality approaches, especially in tasks where movement and force are closely interconnected.[1]

## The Semantic Bridge: Large Language Models in HAR

The integration of Large Language Models (LLMs) represents a paradigm shift from simple action classification to sophisticated behavioral reasoning.[10, 42] While traditional models output a single label (e.g., "walking"), LLM-based HAR can provide interpretability and context-aware descriptions.[10, 43]

The SensorLLM framework exemplifies this trend by using a two-stage alignment process. In the first stage (Sensor-Language Alignment), sensor time-series data is aligned with trend descriptions (e.g., "rapid increase," "stable") generated from statistical analysis.[42] This allows the LLM to ground numerical sensor data into natural language concepts.[10, 42] The second stage (Task-Aware Tuning) refines the model for specific classification tasks without altering the frozen LLM backbone.[42] This framework supports varying sequence lengths and arbitrary channel configurations, offering a "zero-shot" capability to recognize new activities with minimal labeled data.[42, 44]

| LLM Framework | Mechanism | Reported Advantage | Future Outlook |
|---|---|---|---|
| SensorLLM | Two-stage alignment/tuning | Cross-dataset generalizability | Interpretable health monitoring [42] |
| HARGPT | Zero-shot signal prompting | No domain adaptation needed | Rapid prototyping of ADLs [42] |
| LLaSA | Multimodal Agent | Human-like reasoning | Embodied personalization [44] |
| IMUGPT | Text-to-Motion Synthesis | Solves data scarcity | Synthetic training data [42] |

LLMs also address the "black box" nature of traditional deep learning by providing human-readable explanations (XAR—Explainable Activity Recognition). By building on existing XAI models, LLMs can identify the most important semantic features for a given classification and translate them into user-friendly sentences, making them invaluable for clinical environments where clinicians require a rationale for automated health assessments.[43]

## Privacy, Security, and Federated Learning Paradigms

As monitoring systems permeate private spaces such as smart homes and hospitals, ensuring the ethical use of passive sensing is critical.[5, 45] Data captured by these systems can often be used for unauthorized biometric identification of users through unique behavioral traits.[5]

Federated Learning (FL) has emerged as a key technology for privacy-preserving HAR. In an FL setup, the raw data remains on the user's local device; only the model weights or gradients are transmitted to a central server for aggregation.[45, 46] This addresses concerns about data ownership and the reluctance of non-cooperative entities to share sensitive information.[45] Research identifies three additive levels of privacy in HAR:

- **User-Level Privacy:** Prevents the sharing of personal motion data from wearables. This level has minimal impact on accuracy (approximately 5–7% decrease).[45]
- **Environment-Level Privacy:** Protects features that could reveal location information, such as the specific layout of a hospital room. This results in a further accuracy drop of 2–9%.[45]
- **Modality-Level Privacy:** Involves the strict separation of sensor data groups (e.g., separating camera data from audio data). This is the most challenging level, potentially decreasing accuracy by 19–42% unless mitigated by deep mutual learning between modality-specific models.[45]

Techniques like Elastic Weight Consolidation and "Learning Without Forgetting" are employed to handle the feature heterogeneity that arises when models are trained across different hardware landscapes.[45]

## Benchmark Datasets and Evaluation Protocols

Robust evaluation requires large-scale, unconstrained datasets that capture the variability of human behavior. The selection of a dataset often determines the architecture's focus and its ability to generalize to real-world scenarios.[11, 47]

| Dataset | Modalities | Actions / Subjects | Key Challenge |
|---|---|---|---|
| UCF101 | RGB Video | 101 actions / YouTube | Camera motion, clutter [47, 48] |
| NTU RGB+D | RGB, Depth, Skeleton | 60/120 actions / 106 subjects | Perspective variation [19, 24] |
| UCI HAR | IMU (Waist) | 6 actions / 30 subjects | Time-series noise [7, 14] |
| PAMAP2 | IMU, Heart Rate | 12 actions / 9 subjects | Physical intensity variation [11] |
| OPPORTUNITY | Ambient & Wearable | 5/17 actions / 12 subjects | Sensor-rich ADL tracking [11] |
| WISDM | Smartphone IMU | 6 actions / 36 subjects | Realistic device positioning [11] |

The UCF101 dataset remains a gold standard for video-based recognition, featuring clips of sports, musical instruments, and social interactions with significant intra-class variation in actor appearance and scale.[47, 49] For skeleton-based models, NTU RGB+D 120 provides the massive volume of data required for training large graph-based networks.[19, 24]

## Sector-Specific Monitoring Applications

The practical implementation of real-time HAR is transforming workplace safety, healthcare delivery, and large-scale venue management.

### Industrial Safety and Ergonomics

In industrial environments, HAR systems are vital for risk assessment of Manual Material Handling (MMH) tasks.[3] Occupation-related musculoskeletal disorders (WMSDs) often result from repetitive hazardous movements. HAR algorithms, by determining which actions correspond to high biomechanical risk, allow for the automation of workplace ergonomics.[3] Solutions like XMPro integrate wearable data with digital twin technology to simulate safety conditions and predict hazards before they occur, triggering automated alerts to safety managers.[50]

### Clinical Monitoring and Assisted Living

The transition from clinical settings to home-based monitoring is enabled by platforms like Somatix SafeBeing. By detecting hand gestures and ADLs via a lightweight smartwatch, the system monitors hydration, sleep irregularities, and medication compliance for elderly individuals.[51] Immediate alerts for falls or "wandering" (in the case of dementia patients) provide a critical safety net while preserving the patient's independence.[51]

### Workforce Protection and Venue Security

Comprehensive safety networks like Becklar integrate mobile apps and dedicated wearable devices to protect lone workers or personnel in hazardous zones.[52] These systems feature "Worker Down" detection, silent panic buttons, and geofencing breach alerts.[52, 53] In the event of an emergency, the system can provide indoor mapping for precise location tracking, ensuring that response teams are dispatched effectively.[52]

## Strategic Implications and Future Directions

The field of real-time activity recognition is moving toward a future characterized by "contextual intelligence," where systems not only recognize movements but understand the broader narrative of human behavior.[38] The convergence of 5G/6G networking, high-performance edge hardware, and multimodal foundation models is creating a more connected and responsive world.[27, 30]

A critical future direction is the evolution of multi-modal multi-task (M3T) federated foundation models. These models aim to integrate the representational strength of foundation models with the privacy-preserving principles of federated learning.[46] This would allow for embodied personalization, where an AR/VR system or a home robot adapts its recognition capabilities to the specific behavioral patterns and environment of a single user without compromising their privacy.[46]

Another frontier is the development of "agentic" anomaly detection. Conventional systems model a fixed "normal" profile, often missing anomalies that manifest only when multiple data sources are considered jointly.[54] Future systems will utilize LLM-based reasoning to identify subtle departures from normal behavior in complex dynamic environments, such as industrial manufacturing or cybersecurity.[54]

The mathematical rigor of these systems remains paramount. Normalization and standardization procedures are essential to ensure that models remain robust across different users and sensor brands.[17, 55] The use of deep learning has automated the feature engineering process, but the challenge now lies in model interpretability and the management of high-dimensional, heterogeneous data streams in real-time.[14, 38] As these technologies mature, the barrier between human activity and machine perception will continue to dissolve, leading to environments that are safer, more efficient, and more responsive to human needs.

---

## References / Source Links

1. A Comparative Study of Human Activity Recognition: Motion, Tactile, and multi-modal Approaches - arXiv, https://arxiv.org/html/2505.08657v1
2. WatchHAR: Real-time On-device Human Activity Recognition System for Smartwatches, https://arxiv.org/html/2509.04736v1
3. Deep Learning Algorithms for Human Activity Recognition in Manual Material Handling Tasks - MDPI, https://www.mdpi.com/1424-8220/25/21/6705
4. Machine Learning for Human Activity Recognition: State-of-the-Art ..., https://www.mdpi.com/2313-433X/11/3/91
5. Intelligent recognition of human activities using deep learning techniques - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC12021237/
6. A Review on Computer Vision-Based Methods for Human Action ..., https://pmc.ncbi.nlm.nih.gov/articles/PMC8321068/
7. Human Activity Recognition - Using Deep Learning Model - GeeksforGeeks, https://www.geeksforgeeks.org/deep-learning/human-activity-recognition-using-deep-learning-model/
8. Deep Multimodal Learning with Missing Modality: A Survey - arXiv, https://arxiv.org/html/2409.07825v3
9. A Lightweight 3D-CNN for Event-Based Human Action Recognition with Privacy-Preserving Potential - arXiv, https://arxiv.org/html/2511.03665v1
10. On-device Large Multi-modal Agent for Human Activity Recognition - arXiv, https://arxiv.org/html/2512.19742v1
11. Step by Step Towards Effective Human Activity Recognition: A Balance between Energy Consumption and Latency in Health and Wellbeing Applications - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC6928889/
12. A Survey on State-of-the-art Deep Learning Applications and Challenges - arXiv, https://arxiv.org/html/2403.17561v9
13. A Survey on 3D Skeleton-Based Action Recognition Using Learning Method - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC11096730/
14. (PDF) A Deep Learning-based Hybrid CNN-LSTM Model for Human Activity Recognition, https://www.researchgate.net/publication/388517910_A_Deep_Learning-based_Hybrid_CNN-LSTM_Model_for_Human_Activity_Recognition
15. Comparative Evaluation of Deep Learning Architectures for Human Action Recognition, https://computerfraudsecurity.com/index.php/journal/article/view/907
16. Comparative Analysis of Action Recognition Techniques: Exploring Two-Stream CNNs, C3D, LSTM, I3D, Attention Mechanisms, and Hybrid Models - MDPI, https://www.mdpi.com/2673-4591/107/1/43
17. AR3D: Attention Residual 3D Network for Human Action Recognition - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC7957788/
18. (PDF) Comparative Analysis of Fine-Tuning I3D and SlowFast Networks for Action Recognition in Surveillance Videos - ResearchGate, https://www.researchgate.net/publication/377655174_Comparative_Analysis_of_Fine-Tuning_I3D_and_SlowFast_Networks_for_Action_Recognition_in_Surveillance_Videos
19. (PDF) A Survey of Recent Graph-Based Methods for Skeleton ..., https://www.researchgate.net/publication/399580304_A_Survey_of_Recent_Graph-Based_Methods_for_Skeleton-Based_Action_Recognition
20. Adaptive Hyper-Graph Convolution Network for Skeleton-based Human Action Recognition with Virtual Connections - CVF Open Access, https://openaccess.thecvf.com/content/ICCV2025/papers/Zhou_Adaptive_Hyper-Graph_Convolution_Network_for_Skeleton-based_Human_Action_Recognition_with_ICCV_2025_paper.pdf
21. Dynamic Graph Attention Network for Skeleton-Based Action Recognition - MDPI, https://www.mdpi.com/2076-3417/15/9/4929
22. Adaptive Hyper-Graph Convolution Network for Skeleton-based Human Action Recognition with Virtual Connections - arXiv, https://arxiv.org/pdf/2411.14796
23. Semantics-Assisted Training Graph Convolution Network for Skeleton-Based Action Recognition - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC11946682/
24. An enhanced spatial-temporal graph convolution network with high order features for skeleton-based action recognition | PLOS One - Research journals, https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0332815
25. An enhanced spatial-temporal graph convolution network with high order features for skeleton-based action recognition - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC12510661/
26. Real-Time AI Systems Push Engineers to Rethink Latency, Throughput, and Hardware, https://hackernoon.com/real-time-ai-systems-push-engineers-to-rethink-latency-throughput-and-hardware
27. Real Time Adaptive AI pipelines for edge cloud systems: Dynamic optimization based on infrastructure feedback, https://wjaets.com/sites/default/files/fulltext_pdf/WJAETS-2024-0636.pdf
28. Empowering Edge Intelligence: A Comprehensive Survey on On-Device AI Models, https://www.researchgate.net/publication/389927248_Empowering_Edge_Intelligence_A_Comprehensive_Survey_on_On-Device_AI_Models
29. Optimizing Edge AI: A Comprehensive Survey on Data, Model, and System Strategies, https://arxiv.org/html/2501.03265v1/
30. Edge Computing Solutions For Enterprise - NVIDIA, https://www.nvidia.com/en-us/edge-computing/
31. Characterizing the Performance of Accelerated Jetson Edge Devices for Training Deep Learning Models Journal article published in POMACS 2022: Prashanthi S.K, Sai Anuroop Kesanapalli, and Yogesh Simmhan, “Characterizing the Performance of Accelerated Jetson Edge Devices for Training Deep Learning Models,” in Proceedings of the ACM on Measurement and Analysis of Computing Systems, Volume 6, - arXiv, https://arxiv.org/html/2509.20160v1
32. Comparative Analysis of NVIDIA Jetson AGX Orin and RTX 4090: Architectural Distinctions and Performance in AI Applications | lowtouch.ai, https://www.lowtouch.ai/nvidia-jetson-agx-orin-and-rtx-4090-in-ai-applications/
33. 100m Person Detection & Tracking at 35+ FPS on Jetson Orin Nano (8GB), https://forums.developer.nvidia.com/t/100m-person-detection-tracking-at-35-fps-on-jetson-orin-nano-8gb/323764
34. Yolo Speed Test On Jetson: Orin Nano Super • AGX Orin • AGX Thor - YouTube, https://www.youtube.com/watch?v=MnaohuzEuhA
35. Real-Time Human Action Recognition on Embedded Platforms - arXiv, https://arxiv.org/html/2409.05662v1
36. Ultra-Low Latency and Light Speed Performance System Design | by Sourena | Medium, https://medium.com/@SourenAM/ultra-low-latency-and-light-speed-performance-system-design-7b3481ff8ca6
37. NVIDIA Jetson Orin AGX - APIs - ximea support, https://www.ximea.com/support/projects/apis/wiki/NVIDIA_Jetson_Orin_AGX
38. Multi-Modal Data Fusion: Integrating Text, Image, Audio, and Sensor Data in Real-Time Analytics Pipelines, https://datahubanalytics.com/multi-modal-data-fusion-integrating-text-image-audio-and-sensor-data-in-real-time-analytics-pipelines/
39. Multimodal Sensor Fusion Strategy - Emergent Mind, https://www.emergentmind.com/topics/multimodal-sensor-fusion-strategy
40. (PDF) Multimodal Data Fusion Techniques - ResearchGate, https://www.researchgate.net/publication/383887675_Multimodal_Data_Fusion_Techniques
41. Multimodal Models and Fusion - A Complete Guide - Medium, https://medium.com/@raj.pulapakura/multimodal-models-and-fusion-a-complete-guide-225ca91f6861
42. SensorLLM: Aligning Large Language Models with ... - ACL Anthology, https://aclanthology.org/2025.emnlp-main.19.pdf
43. Large Language Models for Human Activity Recognition in Smart-Home - IEEE Xplore, https://ieeexplore.ieee.org/iel8/11038460/11038461/11038588.pdf
44. Ensembling Large Language Models for Human Activity Recognition in Smart Environments, https://www.ulster.ac.uk/doctoralcollege/find-a-phd/11a-computing/older-projects/1680075
45. Privacy in Multimodal Federated Human Activity Recognition - arXiv, https://arxiv.org/abs/2305.12134
46. (PDF) Multi-modal multi-task federated foundation models for next-generation extended reality systems: towards privacy-preserving distributed intelligence in AR/VR/MR - ResearchGate, https://www.researchgate.net/publication/398290073_Multi-modal_multi-task_federated_foundation_models_for_next-generation_extended_reality_systems_towards_privacy-preserving_distributed_intelligence_in_ARVRMR
47. UCF101: Action Recognition Benchmark - Emergent Mind, https://www.emergentmind.com/topics/ucf101-dataset
48. UCF101 Dataset: Annotated videos for action recognition | Innovatiana, https://www.innovatiana.com/en/datasets/ucf101
49. UCF101: A Dataset of 101 Human Actions Classes From Videos in The Wild - ResearchGate, https://www.researchgate.net/publication/233815759_UCF101_A_Dataset_of_101_Human_Actions_Classes_From_Videos_in_The_Wild
50. Real-time Safety Monitoring - XMPRO, https://xmpro.com/solutions-library/other-application-type,other,use-cases/real-time-safety-monitoring/
51. Somatix SafeBeing - Allied Services, https://www.allied-services.org/services/technology-devices/somatix/
52. Employee & Worker Safety Monitoring System - Becklar, https://becklar.com/workforce-safety/
53. Wearable Safety Trackers for Real-Time Venue Protection - Amuse Tech Solutions, https://amusetechsolutions.com/iot-safety-and-crowd-control/wearable-safety-trackers/
54. Agentic and LLM-Based Multimodal Anomaly Detection: Architectures, Challenges, and Prospects - ResearchGate, https://www.researchgate.net/publication/399700415_Agentic_and_LLM-Based_Multimodal_Anomaly_Detection_Architectures_Challenges_and_Prospects
55. Human Activity Recognition (HAR): Fundamentals, Models, Datasets - V7 Labs, https://www.v7labs.com/blog/human-activity-recognition
