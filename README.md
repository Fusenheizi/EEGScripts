MATLAB files (scripts and data) used in Chapter 6 "Spectral and Time-frequency Analyses" of the book "EEG SIGNAL PROCESSING AND FEATURE EXTRACTION"

中文：在《脑电信号处理与特征提取》一书的第5章“频谱分析和时频分析”使用的MATLAB文件（程序和数据）。

Author/作者: Zhiguo Zhang/张治国
Email: zgzhang@szu.edu.cn

第5章 “频谱分析和时频分析” 共有 12 个 Matlab 文件（9 个 “*.m” 脚本文件和 3 个 “*.mat” 数据文件）。以下是文件列表及其说明。

| M 文件                                                       | MAT 文件                               |
| ------------------------------------------------------------ | -------------------------------------- |
| demo_periodogram.m demo_welch.m demo_multitaper.m demo_yulear.m demo_stft.m subfunc_stft.m demo_mwt.m subfunc_mwt.m demo_erserd.m | data_eeg.mat data_vep.mat data_lep.mat |

## M 文件

- **demo_periodogram.m**：该脚本用于演示如何使用周期图法估计 EEG 信号的频谱。运行此脚本可从 data_eeg.mat 读取 EEG 信号，计算其周期图，并以线性和对数尺度显示结果。
- **demo_welch.m**：该脚本用于演示如何使用 Welch 方法估计 EEG 信号的频谱。运行此脚本可从 data_eeg.mat 读取 EEG 信号，使用不同参数计算其 Welch 频谱，并显示结果。
- **demo_multitaper.m**：该脚本用于演示如何使用多窗谱估计法估计 EEG 信号的频谱。运行此脚本可从 data_eeg.mat 读取 EEG 信号，使用不同参数计算其多窗频谱，并显示结果。
- **demo_yulear.m**：该脚本用于演示如何使用 Yule-Walker 算法的自回归（AR）方法估计 EEG 信号的频谱。运行此脚本可从 data_eeg.mat 读取 EEG 信号，使用不同模型阶数计算其 AR 频谱，并显示结果。
- **demo_stft.m**：该脚本用于演示如何使用短时傅里叶变换（STFT）估计视觉诱发电位（VEP）信号的时频分布。运行此脚本可从 data_vep.mat 读取 VEP 信号，使用不同窗口大小计算其 STFT，并显示结果。此脚本需要调用同一文件夹中的子函数 subfunc_stft.m。
- **subfunc_stft.m**：该子函数用于使用用户定义的参数计算时间序列信号的 STFT。该函数输入和输出的所有详细信息都在 M 文件中给出。
- **demo_mwt.m**：该脚本用于演示如何使用 Morlet 小波基的连续小波变换（CWT）估计视觉诱发电位（VEP）信号的时频分布。运行此脚本可从 data_vep.mat 读取 VEP 信号，使用不同小波参数计算其 CWT，并显示结果。此脚本需要调用同一文件夹中的子函数 subfunc_mwt.m。
- **subfunc_mwt.m**：该子函数用于使用用户定义的参数，基于 Morlet 小波基计算时间序列信号的 CWT。该函数输入和输出的所有详细信息都在 M 文件中给出。
- **demo_erserd.m**：该脚本用于演示如何使用 STFT 估计多次激光诱发电位（LEP）信号试验的事件相关同步 / 去同步（ERS/ERD）。运行此脚本可从 data_lep.mat 读取 LEP 试验数据，计算其功率和相位的时频分布，进行基线校正（有四种可能的方法），并显示 LEP、ERS/ERD 和锁相值（PLV）的结果。此脚本需要调用同一文件夹中的子函数 subfunc_stft.m。

## MAT 文件

- data_eeg.m

  ：此 EEG 数据文件包含两个变量。

  - **x**：在闭眼状态下，Oz 位置记录的一段短时间 EEG 试验数据（有 480 个时间点）；
  - **Fs**：EEG 信号的采样率，为 160Hz。

- data_vep.m

  ：此 VEP 数据文件包含三个变量。

  - **x**：VEP 数据（512 个时间点）；
  - **Fs**：VEP 数据的采样率，为 250Hz；
  - **t**：VEP 数据的时间索引（刺激前 256 个样本，刺激后 256 个样本，时间间隔为 1/Fs）。
  - **注意**：原始 VEP 数据来自https://vis.caltech.edu/~rodri/data/cg_o1t.asc。有关数据的更多详细信息，请参见https://vis.caltech.edu/~rodri/data.htm。

- data_lep.m

  ：此 LEP 数据文件包含三个变量。

  - **x**：在对侧 EEG 电极（C3 或 C4）记录的 LEP 数据，维度为 512×74（512 为时间点数，74 为试验次数）；
  - **Fs**：LEP 数据的采样率，为 256Hz；
  - **t**：LEP 数据的时间索引（刺激前 256 个样本，刺激后 256 个样本，时间间隔为 1/Fs）。
  - **注意**：有关 LEP 数据的更多详细信息，可查阅 Zhang, Hu 等人发表于《Journal of Neuroscience》2012 年第 32 卷第 22 期，7429 - 7438 页的 “Gamma-Band Oscillations in the Primary Somatosensory Cortex-A Direct and Obligatory Correlate of Subjective Pain Intensity” 一文。
