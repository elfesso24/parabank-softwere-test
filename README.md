# ParaBank Testing Documentation Software Testing Project Report



# Software Testing Project Documentation
**Course**: CS414 – Software Testing
**System Under Test**: ParaBank (Web UI)
**Tester**: Feras Gsiea
**Submission Date**: 2025-02-27 

****

---



## Introduction
This project focuses on testing the ParaBank web application to identify functional and non functional defects  : 

**functional tests**: 

1. **Customer Login** 
2. **Contact Page**
3. **Withdraw Funds** 
4. **Contact Page Submission** 
5. **Open New Account** 
6. **Transfer Funds**
7. **Bill Payement Service**


**Non function test **: 

1. **Performance**
2. **security**
---

## Test Environment
| **Component** | **Details** |
| ----- | ----- |
| **Browser** | Brave Browser |
| **OS** | Windows 11, Android 14 |
| **Device** | Desktop, Mobile |
| **Country/City** | Libya, Tripoli |
| **Tools Used** | Brave Browser Inspector, JMeter |
---

## Test Execution Summary
| **Total Test Cases** | **Passed** | **Failed** | **Pass Rate** |
| ----- | ----- | ----- | ----- |
| 15 | 9 | 6 | 60% |
**Failed Test Cases**: 

- `Ts_01` , `Ts_02`  (Login Issues) 
- `Ts_06`  (Withdrawal Failure) 
- `Ts_12` , `Ts_13`  (Fund Transfer Errors) 
- `Ts_14`  (Account Overview Inconsistencies)
---

## Test Cases Design & Execution
### Foundational Requirements Tested
#### 1. **Customer Login**
| TC ID | Scenario | Input Data | Expected Result | Actual Result | Status |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Ts_01 | Valid Credentials |  | Redirect to Account Overview | <p>Redirected but balance showed </p><p>**$100,000**</p><p> (incorrect)</p> | Fail |
| Ts_02 | Valid Credentials (Mobile) |  | Redirect to Account Overview | Logged in but displayed "Username already exists" | Fail |
| Ts_03 | Invalid Password |  | Error: Invalid credentials | Error shown: "Could not be verified" | Pass |
---

**Screenshot Placeholder**: 

- `Ts_01` : Incorrect balance after login. 


![Screenshot 2025-02-26 223240.png](https://eraser.imgix.net/workspaces/7fctoHUzlESimBJAuklS/3Tl3y7k0LGPg1Pb3jedwFSY7RAm1/7MZnPPPOQN0Z4YwXuM1Qc.png?ixlib=js-3.7.0 "Screenshot 2025-02-26 223240.png")

---

- `Ts_02`: "Username already exists" error on mobile.


![photo_5909083158106720238_y.jpg](https://eraser.imgix.net/workspaces/7fctoHUzlESimBJAuklS/3Tl3y7k0LGPg1Pb3jedwFSY7RAm1/KutFMdByxwtbncYWrG9PE.jpg?ixlib=js-3.7.0 "photo_5909083158106720238_y.jpg")

---

#### 2. **Withdraw Funds**
| TC ID | Scenario | Steps | Expected Result | Actual Result | Status |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Ts_06 | Access Withdrawal Interface | <p>1. Login</p><p><br /></p><p>2. Navigate to Withdraw</p> | Redirect to interface | XML Error: "No style information associated" | Fail |
- `Ts_06` : XML error on withdrawal page.


![Screenshot 2025-02-27 152414.png](https://eraser.imgix.net/workspaces/7fctoHUzlESimBJAuklS/3Tl3y7k0LGPg1Pb3jedwFSY7RAm1/s8ZCzt9XoMLRZIqybdDPx.png?ixlib=js-3.7.0 "Screenshot 2025-02-27 152414.png")

---

#### 3. **Transfer Funds**
| TC ID | Scenario | Input Data | Expected Result | Actual Result | Status |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Ts_12 | Transfer to Same Account |  | Error: Same account transfer | <p>Transfer succeeded: </p><p>**$1,000 moved between same account**</p> | Fail |
| Ts_13 | Overdraft Transfer |  | Error: Insufficient funds | <p>Transfer allowed: </p><p>**$1,000,000,000,000 transferred**</p> | Fail |
- `Ts_12` : Successful transfer to the same account. 


![Screenshot 2025-02-26 232616.png](https://eraser.imgix.net/workspaces/7fctoHUzlESimBJAuklS/3Tl3y7k0LGPg1Pb3jedwFSY7RAm1/bI0vQvNJU9d6BpVoWwuVq.png?ixlib=js-3.7.0 "Screenshot 2025-02-26 232616.png")

- `Ts_13`: Exceeding balance transfer.


![Screenshot 2025-02-26 232910.png](https://eraser.imgix.net/workspaces/7fctoHUzlESimBJAuklS/3Tl3y7k0LGPg1Pb3jedwFSY7RAm1/L-Lkpmfxxd8TglKfwAKDj.png?ixlib=js-3.7.0 "Screenshot 2025-02-26 232910.png")

---

## Bug Reports
### Critical Bugs Identified
| Bug ID | Component | Summary | Severity |
| ----- | ----- | ----- | ----- |
| Bug_01 | Customer Login | Incorrect balance displayed after login | Critical |
| Bug_02 | Customer Login | "Username already exists" error on valid credentials (mobile) | Critical |
| Bug_03 | Withdraw Funds | XML error prevents withdrawal | Critical |
| Bug_04 | Transfer Funds | Allowed transfer to the same account | Critical |
| Bug_05 | Transfer Funds | Allowed overdraft beyond account balance | Critical |
| Bug_06 | Account Overview | Negative balance and unrealistic available balance displayed | Critical |
---

****## Test Cases Execution (Non function)
### 1. Performance: 
#### **reload speed :**


![Screenshot 2025-02-27 162748.png](https://eraser.imgix.net/workspaces/7fctoHUzlESimBJAuklS/3Tl3y7k0LGPg1Pb3jedwFSY7RAm1/LLQogzzopISnuZrTg28z_.png?ixlib=js-3.7.0 "Screenshot 2025-02-27 162748.png")

Tool used : browser inspector (inspect element)

the reload speed was 1.5 seconds to reload and the file size was about 1.5kb, the time is considered good because of  my bad internet connection



#### second try :


![image.png](https://eraser.imgix.net/workspaces/7fctoHUzlESimBJAuklS/3Tl3y7k0LGPg1Pb3jedwFSY7RAm1/Mwt3euUiFpc_LoYsBFyxg.png?ixlib=js-3.7.0 "image.png")

the reload speed for the second performance test 1.11 second for the same page so reload performance is pretty good

---

### **2.security:**
Iv used Hostedscan from [﻿hostedscan.com/owasp-vulnerability-scan ](https://hostedscan.com/owasp-vulnerability-scan) this website has strong testing tools integrated such as OPEN VAS lite version for non subscribers for vulnerability scans, OWASP ZAP , nmap for open ports and network scanning this website provides exclusive reports that i will add to the submit file :



![Screenshot 2025-02-27 190238.png](https://eraser.imgix.net/workspaces/7fctoHUzlESimBJAuklS/3Tl3y7k0LGPg1Pb3jedwFSY7RAm1/hKs3K03cmhtUn-N0BTuBR.png?ixlib=js-3.7.0 "Screenshot 2025-02-27 190238.png")



![Screenshot 2025-02-27 182513.png](https://eraser.imgix.net/workspaces/7fctoHUzlESimBJAuklS/3Tl3y7k0LGPg1Pb3jedwFSY7RAm1/lo-8FdXUq2FkBjMrs5Iv9.png?ixlib=js-3.7.0 "Screenshot 2025-02-27 182513.png")



nmap discovered 3 ports that are exploited :

tcp ports : 8443,8080 ,443



---

## Coverage Methodology
### Testing Strategies
- **Functional Testing**: Validated core features (login, transactions).
- **Non functional Testing:** validated availability (reload speed) and security   
- **Boundary Testing**: Tested overdraft scenarios (e.g., `Ts_13` ). 
- **Negative Testing**: Invalid credentials (`Ts_03` , `Ts_04` ).


## 




---



