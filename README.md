For Detailed Description please visit : https://medium.com/@goyal.shubhangi/an-overview-anomaly-detection-304deaa199bb - automatic!
[Medium Link](https://medium.com/@goyal.shubhangi/an-overview-anomaly-detection-304deaa199bb)

# Anomaly Detection

Anomaly detection (also known as outlier detection) is the process of finding data objects with behaviours that are very different from expectation. Such objects are called anomalies.

Suppose, Payment Processor Companies (like PayPal) keeps a track of your usage pattern (such as transaction amounts, location of transaction, etc.) so as to notify in case of any dramatic change in the usage pattern. Now, if a credit card is stolen, it is very likely that the transactions may vary largely from the usual ones , this is where the companies detect unusual transactions that may take place after the credit card theft. Such values are referred to as Anomalies or Outliers or Anomalous Data.


## ASPECTS OF ANOMALIES
### Input Data
The Input Data can be of either univariate or multivariate, as follows-

i) **Univariate outliers** can be found when looking at a distribution of values in a single feature space. 

ii) **Multivariate outliers** can be found in a n-dimensional space (of n-features). Looking at distributions in n-dimensional spaces can be very difficult for the human brain, that is why we need to train a model to do it for us.

### Types of Anomalies
The nature of the desired anomaly can be classified into three types-

i) **Global Anomalies:** They correspond to the data points which deviate largely from the rest of the data points. However, a key challenge in detecting global anomalies is to figure out the exact amount of deviation which leads to a potential anomaly.
For example, A banking customer who normally deposits no more than $1000 a month in checks at a local ATM suddenly makes two cash deposits of $5000 each in the span of two weeks is a global anomaly because this event has never before occurred in this customer’s history. The time series data of their weekly deposits would show an abrupt recent spike. Such a drastic change would raise alarms as these large deposits could imply illicit commerce or money laundering.

ii) **Contextual/Conditional Anomalies:** A data point is considered a contextual outlier if its value significantly deviates from the rest of the data points in the same context. The deviation that leads to the anomaly depends on information governed by contextual and behavioral attributes. And also, these values are not outside the normal global range, but are abnormal compared to the seasonal pattern. 
Suppose, There is a sudden surge in order volume at an eCommerce company, compare to as seen in that company’s hourly total orders. So, this could be if high volume occurs outside of a known promotional discount or high volume period like Black Friday, or Could this stampede be due to a pricing glitch which is allowing customers to pay pennies on the dollar for a product, then this would be contextual anomaly.

iii) **Collective Anomaly:** The main idea behind collective anomalies is that the data points included in forming the collection may not be anomalies when considered individually. These are interesting because here we not only look at individual data points but also analyse their behaviour in a collective order.
For example, A publicly traded company’s stock is never a static thing, even when prices are relatively stable and there isn’t an overall trend. If the stock price remained at exactly the same price for an extended period of time, then that would be a collective outlier.

### Output Data
For the output purpose, most approaches will give-
i) **Score:** In Scoring techniques analyst can choose values which are more suitable for the problem area and later, use the threshold value to select anomalies or just choose the top ones. 
ii) **Label:** Labelling is a classification, no approaches by now can be used in all domains with the same success without research about the domain and feature extraction.

## DETECTION APPROACHES
Data can be of any form practically — structured, semi-structured and unstructured. So, approaches that can be used to find anomalies fall into following categories:

i) **Supervised Anomaly Detection:** When the data is labelled in training and test datasets it comes under the supervised learning approach to find the anomalies.
However, this setup is not relevant, because we need to know all anomalies and label data correctly. For many cases anomalies are not known in advance or may occur as novelties during the test phase.

ii) **Semi-Supervised Anomaly Detection:** In the beginning, there is no knowledge thus training results. This setup uses training and test datasets, where only training data consists of normal data without any anomalies. The idea is, a model of the normal class is already taught and anomalies can be detected by deviating from learned model. 
Example of such approach are One-class SVMs and Autoencoder. Any density estimation approach can be applied to model the probability density function of the normal classes, such as Gaussian Mixture approaches or KD Estimation.

iii) **UnSupervised Anomaly Detection:** When their is no knowledge of what is normal in the data and what is not, thus no difference between a training and a test dataset. Typically, distances or densities are used to give an evaluation what is normal and what is an outlier.
Such detection can be implmented via Nearest-neighbor base(like kNN), Clustering based , Statistical based, Subspace-based and Classifier based(like One-class SVM) approaches.

## APPLICATIONS
The way anomalies are generated, it hugely varies from domain to domain, application to application. Let’s review some of the fields where anomaly detection is vital -

i) **Intrusion detection :** It refers to detection of malicious activity (break-ins, penetrations, etc.) in a computer system. An intrusion is different from the normal behavior of the system, and hence anomaly detection techniques are applicable in intrusion detection domain. It can be classified into host-based (here, anomalous subsequences translate to malicious programs, unauthorised behaviour and policy violations)and network-based(here, attacks are launched by outside hackers who want to gain unauthorized access to the network for information theft or to disrupt the network) intrusion detection systems.

ii) **Fraud detection :** Fraud detection refers to detection of criminal activities occurring in commercial organisations which can include applications such as credit-card fraud, mobile phone fraud, insurance claim fraud, insider trading detection, etc. 

iii) **Medical and Health :** The data can have anomalies due to several reasons, such as abnormal patient condition, instrumentation errors, or recording errors. Several techniques have also focussed on detecting disease outbreaks, Electrocardiograms (ECG) fluctuations, etc.

iv) **Industrial Damage :** The damage due to continuous usage and normal wear & tear in industrial units. Applications includes Fault in mechanical units, structural defect in good, etc.

v) **Electronic sensor events :** Electronic sensors(such as light sensors, accelerometer, proximity sensors, ultrasonic sensors, etc) enable us to capture data from various sources. But sometimes the sensor becomes dysfunctional, it fails to capture the data in the correct way and thus produces anomalies. When these sensors start to behave inconsistently the signals they convey get also uncanny, thereby causing unprecedented troubleshooting.

## CHALLENGES IN ANOMALY DETECTION
On the abstract level detection of the anomalies seems like a simple task. But this task can be very challenging. Here are some challenges bellow:

**→** Defining a normal region that encompasses every possible normal behavior is very difficult. In many cases boundaries between anomalies and normal data are not precise. In this case, normal observations could be considered as anomalies, and vice-versa.

**→** If action is malicious, like fraud, it is considered as anomaly. Very often attackers try to adapt their actions to the normal behaviour, thereby making the task of defining normal behavior more difficult.

**→** In many domains normal behaviour keeps evolving and a current notion of normal behaviour might not be sufficiently representative in the future.

**→** Approaches for anomaly detection in one field more often cannot be used in the other one, ie., The exact notion of an anomaly is different for different application domains.

**→** Often the data contains noise that tends to be similar to the actual anomalies and hence is difficult to distinguish and remove.
