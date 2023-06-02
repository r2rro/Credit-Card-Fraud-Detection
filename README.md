## Introduction

In this [project](https://www.kaggle.com/competitions/ieee-fraud-detection/data), we are predicting the probability that an online transaction is fraudulent, as denoted by the binary target isFraud.

The data is broken into two files identity and transaction, which are joined by TransactionID. Not all transactions have corresponding identity information.


* **TransactionDT**: timedelta from a given reference datetime (not an actual timestamp)
* **TransactionAMT**: transaction payment amount in USD
* **ProductCD**: product code, the product for each transaction
* **card1 - card6**: payment card information, such as card type, card category, issue bank, country, etc.
* **addr**: address
* **dist**: distance
* **P_ and (R__) emaildomain**: purchaser and recipient email domain
* **C1-C14**: counting, such as how many addresses are found to be associated with the payment card, etc. The actual meaning is masked.
* **D1-D15**: timedelta, such as days between previous transaction, etc.
* **M1-M9**: match, such as names on card and address, etc.
* **Vxxx**: Vesta engineered rich features, including ranking, counting, and other entity relations.

## Categorical Features - Transaction

* ProductCD
* card1 - card6
* addr1, addr2
* R_emaildomain
* M1 - M9

Variables in identity table are network connection information (IP, ISP, Proxy, etc) and digital signature (UA/browser/os/version, etc) associated with transactions.
They're collected by Vesta’s fraud protection system and digital security partners and are masked for privacy purposes.

## Categorical Features - Identity

* DeviceType
* DeviceInfo
* id_12 - id_38

The TransactionDT feature is a timedelta from a given reference datetime.

**train_{transaction, identity}.csv** - the training set

**test_{transaction, identity}.csv** - the test set (you must predict the isFraud value for these observations)

## Classification Results

**sample_submission.csv** - a sample submission file in the correct format
