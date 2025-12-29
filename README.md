# AWS-!

 EC2 = **Rent a server on AWS, scalable and pay-as-you-go**

**Amazon EC2** 

- Virtual Server (VM) ပေးသည်
- မိနစ်အနည်းငယ်အတွင်း Server တည်ဆောက်နိုင်
- လိုအပ်သလို Auto Scale လုပ်နိုင်
- သုံးသလောက်ပဲ ငွေပေးရ (Pay-as-you-go)

---

**EC2 Instances – Easy Explanation (Myanmar)**

ဒီပုံက **Amazon EC2 ဘယ်လိုအလုပ်လုပ်လဲ** ဆိုတာကို ရိုးရိုးလေး ပြထားတာပါ 👇

- **Internet / AWS Services**
    
    👉 User တွေက Internet ကနေ AWS ကို ဝင်လာပါတယ်
    
- **Network Device**
    
    👉 Traffic (data) တွေကို EC2 server ဆီ ပို့ပေးတဲ့ network လမ်းကြောင်းပါ
    
- **Hypervisor**
    
    👉 Physical Server တစ်လုံးကို **EC2 Instances (Virtual Servers)** အများကြီး ခွဲသုံးနိုင်အောင် လုပ်ပေးတဲ့ software ပါ
    
    👉 EC2 တစ်လုံးစီကို သီးသန့် server လို သုံးနိုင်ပါတယ်
    
- **EC2 Instances**
    
    👉 သင် create လုပ်တဲ့ Virtual Servers တွေ
    
    👉 Website, App, Database စတာတွေ run လုပ်နိုင်
    
- **CPUs / Memory (RAM)**
    
    👉 EC2 Instance အလုပ်လုပ်ဖို့ လိုအပ်တဲ့ Processing Power နဲ့ Memory
    
- **Instance Store**
    
    👉 EC2 အတွက် temporary storage
    
    👉 Instance stop/delete လုပ်ရင် data ပျောက်နိုင်
    
- **EBS (Elastic Block Store)**
    
    👉 EC2 အတွက် permanent storage
    
    👉 Instance ပိတ်ရင်တောင် data မပျောက်
    

**အကျဉ်းချုပ်**

👉 AWS မှာ Physical Server တစ်လုံးကို Hypervisor နဲ့ ခွဲပြီး

👉 EC2 (Virtual Servers) အများကြီး သုံးနိုင်အောင် လုပ်ထားတာပါ

---

### EC2 Provisioning

- **AMI** – OS + software
- **Instance Type** – CPU/RAM size
- **Key Pair** – Login key
- **VPC (Network)** – IP/subnet setup
- **Security Group** – Firewall rules
- **Storage** – EBS (permanent) / Instance Store (temporary)
- **IAM Role** – AWS service access———————
- **User Data** – Startup script—————————

---

ရပါတယ်၊ အဲ့ဒီလိုဆိုရင် **title ကို အတိုချုံး အညွှန်း မထည့်ဘဲ** ဖော်ပြနိုင်ပါတယ် –

---

### **Amazon EC2 & AMI  ( ova in vm area /// java cd )**

- **AMI (Amazon Machine Image):** OS, apps, settings ပါတဲ့ template.
- **EC2 တစ်ခု launch ဖို့ Source AMI လိုပါတယ်။**
- **တစ်ခု AMI → အများကြီး instance လွှတ်နိုင်**၊ မတူ AMI → မတူ instance type.
- **Custom AMI:** ကိုယ့် EC2 ကနေ ဖန်တီးပြီး setup များ reuse လို့ရ.
- **EC2 Instance:** AMI ကနေ launch လုပ်တဲ့ virtual server.

---

:**AMI ထဲမှာ ပါဝင်တာများ**

1. **Root Volume Template** – Instance အတွက် အခြေခံ storage.
2. **Full Operating System** – Linux, Windows စသည်တို့.
3. **Installed Software & Applications** – OS ထဲမှာ အရင်တင်ပြီးသား software တွေ.
4. **Launch Permissions** – ဘယ် AWS account တွေ AMI ကို အသုံးပြုနိုင်မယ် ဆိုတာ control လုပ်နိုင်.
5. **Block Device Mapping** – အချိန်တိကျစွာ storage volumes တွေ instance နဲ့ attach လုပ်ပေးနိုင်မှု.

**အကျဉ်းချုပ်:** AMI က **EC2 instance တစ်ခု launch လုပ်ဖို့ လိုအပ်တဲ့ အရာအားလုံး** ပါဝင်ပါတယ်။

---

---

### **EC2 Image Builder**

- **Purpose:** VM & container images ကို AWS / on-premises အတွက် build, test, deploy လုပ်ရန်.
- **Source Image:** AWS templates သို့ custom templates.
- **Customize:** Image ထဲ software ကို ပြင်နိုင်.
- **Test & Distribute:** စမ်းသပ်ပြီး trusted images ဖြန့်နိုင်.

**Golden Image:**

- Pre-configured, tested, trusted image ဖြစ်ပြီး **production အတွက် အသုံးပြုနိုင်တဲ့ standard template**.

---

### **EC2 User Data (one time )**

- **Purpose:** EC2 launch အချိန်မှာ **automatic scripts run**.

---

### **EC2 EBS Volume**

- **Block Storage:** Hard driveလို data store
- **Persistent:** EC2 stop/delete → data မပျောက်
- **Instance Store vs EBS:** Instance Store = temporary, EBS = permanent
- **Attachment:** Multiple EBS → 1 instance, 1 EBS → only 1 instance

**Summary:** EBS = EC2 အတွက် **permanent block-level storage**

---

### **EC2 Storage Types**

**1. Instance Store**

- Temporary block-level storage
- Physically attached to host server
- Data **ပျောက်နိုင်** when instance stops/terminates
- Best for **temporary or frequently changing data**

**2. EBS Volume**

- Persistent, detachable block-level storage
- Survives instance stop/terminate
- Can run **database**, or backup instance into **AMI**
- Each volume attaches to **one instance at a time**, multiple volumes per instance allowed

**Summary:**

> Instance Store = temporary storage, EBS = permanent storage for EC2.
> 

---

### **Amazon EBS SSD Types – Short Table**

| **Type** | **Use** | **Example** |
| --- | --- | --- |
| **gpSSD** | General purpose | Medium DB, Dev/Test, Boot volumes |
| **ioSSD** | High performance | Large DB, Critical apps, Low-latency workloads |

**Summary:** gpSSD = balanced, =⇒ no need hpc 

 ioSSD = high-performance

---

### **Amazon EBS HDD Types – Short Table**

| **Type** | **Description** | **Use Cases** |
| --- | --- | --- |
| **Throughput Optimized HDD (st1)** | Low-cost HDD for frequently accessed, throughput-intensive workloads | Big data, Data warehouses, Log processing (cannot be boot volume) |
| **Cold HDD (sc1)** | Lowest-cost HDD for infrequently accessed data | Archival storage, Low-cost data storage (cannot be boot volume) |

**Summary:**

- **st1** = throughput-oriented, frequently accessed data
- **sc1** = cost-optimized, infrequently accessed data

---

Share file System 

Linux      =  EFS

window  = FSX 

---
### **EC2 Instance Sizes – Short Table**

| **Model**      | **vCPU** |
| -------------- | -------- |
| **wlarge**     | 2        |
| **m5xlarge**   | 4        |
| **m5.2xlarge** | 8        |
| **m5.8xlarge** | 32       |
----------------------------

































