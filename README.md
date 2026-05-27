# FleetMind：AI Logistics Assistant 🚚📊

由本人手搓出来的轻量级物流分析 Web App。

简单来说，FleetMind 是一个帮助分析卡车运营数据的小工具。它可以根据车辆的收入、燃油费、过路费、维修费、工资、保险费和其他成本，计算利润、利润率、风险等级，并找出主要成本压力。

项目灵感来自我自己接触过的物流业务和实习/工作经验。虽然目前还不是那种类似LLM、或者其他类似专业的的系统，但我也算成功将一个python小程序，从terminal上运行，到把它升级成能了一个小型网页，并且能够实际应用了！

---

## 项目简介

在传统物流业务里，很多经营判断其实都和这些问题有关：

- 这辆车到底赚不赚钱？
- 成本主要高在哪里？
- 哪条路线风险比较大？
- 这辆车利润率低，是收入不够，还是成本太猛？
- 有没有一个简单工具可以帮我快速看出问题？

FleetMind 就是围绕这些问题做的。

用户可以在网页里输入一辆车的运营数据，系统会自动分析：

- 总成本
- 利润
- 利润率
- 风险等级
- 主要成本压力
- 简单经营建议

虽然它现在还不是一个真正的大模型 AI，但里面有一个 keyword-based AI assistant，可以回答一些基础物流经营问题，比如 fuel cost、profit、risk、route、repair cost 等。

---

## 功能展示

### 1. Analyse a Sample Truck

系统内置了 12 辆匿名化样本车。

用户可以选择其中一辆车，查看它的详细分析结果。

包括：

- Truck ID
- Driver
- Route
- Revenue
- Total Cost
- Profit
- Profit Margin
- Risk Level
- Main Cost Pressure
- Suggestion

适合用来快速展示项目功能。

---

### 2. Add and Analyse a New Truck

用户可以自己输入一辆新车的数据，例如：

- Truck ID
- Driver
- Route
- Revenue
- Fuel Cost
- Toll Cost
- Repair Cost
- Salary Cost
- Insurance Cost
- Other Cost

提交后，FleetMind 会自动生成分析结果。

说人话就是：

> 你把数据填进去，它帮你算账。  
> 算完以后还会告诉你：兄弟，这车到底香不香。

---

### 3. Compare Sample Trucks

系统会对所有 sample trucks 按照利润率进行排序。

页面会显示：

- Best Performing Truck
- Highest Risk Truck
- Truck Ranking Table

这个功能主要用来快速比较不同车辆的经营表现。

比如系统可能会告诉你：

> Truck 003 是目前表现最好的车。  
> Truck 007 风险比较高，建议老板别装看不见。

---

### 4. AI Logistics Assistant

这是一个基于关键词的简单 AI 小助手。

它可以回答一些基础问题，例如：

- Why is fuel cost high?
- How can I reduce business risk?
- Why is profit margin low?
- How should I understand route cost?

目前它不是接入 ChatGPT API 的真正大模型版本，而是一个 rule-based / keyword-based assistant。

但是作为学生项目第一版，它已经可以表达一个基本思路：

> 先用规则实现简单 AI 逻辑，后面可以继续升级成真正的 LLM assistant。

---

### 5. Analysis History

每次分析车辆后，系统会把分析结果保存到 `fleet_history.txt`。

用户可以在网页里查看历史记录。

目前使用的是普通 txt 文件保存，不是数据库。  
主打一个：

> 先让它跑起来，再让它高级起来。

---

## 技术栈

这个项目使用了：

- Python
- Flask
- HTML
- CSS
- File Handling
- Object-Oriented Programming

项目中用到了 Python 基础知识：

- class
- method
- function
- list
- dictionary
- conditionals
- file read/write
- string formatting
- Flask route
- HTML form
- Jinja template

---

## 项目结构

```text
FleetMind-Web/
│
├── app.py
├── fleetmind_core.py
├── fleet_history.txt
│
├── templates/
│   ├── index.html
│   ├── samples.html
│   ├── result.html
│   ├── new_truck.html
│   ├── compare.html
│   ├── assistant.html
│   └── history.html
│
├── static/
│   └── style.css
│
└── README.md