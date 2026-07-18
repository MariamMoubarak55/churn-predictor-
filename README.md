<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Streamlit-1.50%2B-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit">
  <img src="https://img.shields.io/badge/scikit--learn-1.5%2B-F7931E?logo=scikit-learn&logoColor=white" alt="scikit-learn">
  <img src="https://img.shields.io/badge/model-Random%20Forest-831C91" alt="Model">
  <img src="https://img.shields.io/badge/accuracy-86.8%25-success" alt="Accuracy">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="License">
</p>

<h1 align="center">🏦 Bank Churn Predictor</h1>

<p align="center">
  <b>تطبيق ويب تفاعلي لتوقع احتمالية مغادرة عملاء البنك</b><br>
  مبني بـ Streamlit + Random Forest — بواجهة احترافية داكنة بتصميم Neon Purple
</p>

---

## 🎯 نظرة عامة

**Bank Churn Predictor** هو أداة تحليلات تنبؤية (Predictive Analytics) بتساعد البنوك والمؤسسات المالية إنها تتعرف على العملاء اللي عندهم احتمالية عالية إنهم يسيبوا البنك (Customer Churn)، وده من خلال إدخال بيانات العميل والحصول على توقع فوري مع نسبة الاحتمالية.

المشروع مش مجرد موديل ML — ده تطبيق كامل بواجهة مستخدم احترافية، تصميم عصري، وتجربة مستخدم سلسة.

---

## ✨ المميزات

- 🎨 **واجهة مستخدم احترافية** — تصميم داكن بتدرجات أرجواني (Neon Purple Dark Theme)، خط Space Grotesk، زراير gradient، كروت نتائج animated
- ⚡ **توقع فوري** — بمجرد ما تدخل بيانات العميل وتضغط زر، يظهر التوقع في أقل من ثانية
- 📊 **عرض احتمالي مزدوج** — نسبة بقاء العميل ونسبة مغادرته في كروت منفصلة جنب بعض
- 📱 **متجاوب بالكامل** — Responsive design بيشتغل على الموبايل والتابلت والديسكتوب
- 🔍 **تفاصيل تقنية** — Expander مدمج بيعرض البيانات المدخلة والـ raw prediction
- 🧠 **موديل متكامل** — Scikit-learn Pipeline (StandardScaler + OneHotEncoder + Random Forest)
- 🚀 **تحميل الموديل مرة واحدة** — `@st.cache_resource` عشان أداء سريع ومفيش reload

---

## 🧰 التقنيات المستخدمة

| التقنية | الاستخدام |
|---------|-----------|
| **Python 3.10+** | لغة البرمجة الأساسية |
| **Streamlit** | إطار عمل الواجهة التفاعلية |
| **scikit-learn** | تدريب الموديل + Pipeline |
| **pandas** | معالجة البيانات المدخلة |
| **NumPy** | العمليات الحسابية |
| **joblib** | حفظ وتحميل الموديل |
| **Random Forest** | الخوارزمية المستخدمة للتوقع |
| **CSS3** | تنسيق الواجهة المخصص |

---

## 🗂️ هيكل المشروع

```
churn-predictor/
├── app_dashboard.py              # تطبيق Streamlit — الواجهة + الـ logic
├── bank_churn_model_full.pkl     # الموديل المدرب (Pipeline كامل)
├── requirements.txt              # المكتبات المطلوبة
└── README.md                     # التوثيق (الملف ده)
```

---

## ⚙️ التثبيت والتشغيل

### المتطلبات الأساسية

- Python 3.10 أو أحدث
- pip (مدير حزم Python)

### خطوات التشغيل

```bash
# 1. استنسخ المشروع
git clone https://github.com/keroles-salah/churn-predictor.git
cd churn-predictor

# 2. ثبت المكتبات المطلوبة
pip install -r requirements.txt

# 3. شغّل التطبيق
streamlit run app_dashboard.py

# 4. افتح المتصفح
# http://localhost:8501
```

---

## 🎮 طريقة الاستخدام

1. **افتح التطبيق** في المتصفح بعد تشغيل `streamlit run`
2. **املأ بيانات العميل** في الـ 10 حقول:
   - **Credit Score** — الدرجة الائتمانية (350–850)
   - **Age** — العمر (18–100)
   - **Tenure** — عدد سنوات التعامل مع البنك (0–10)
   - **Balance** — الرصيد بالدولار (0–300,000)
   - **Estimated Salary** — الراتب التقديري (0–300,000)
   - **Number of Products** — عدد المنتجات المشترك فيها (1–4)
   - **Geography** — الدولة (France, Germany, Spain)
   - **Gender** — النوع (Female, Male)
   - **Has Credit Card** — هل معاه بطاقة ائتمان؟
   - **Is Active Member** — هل هو عضو نشط؟
3. **اضغط زر "Predict Churn"**
4. **شوف النتيجة فوراً** — العميل عالي الخطورة (High Risk) ولا منخفض الخطورة (Low Risk)، مع نسبة الاحتمالية المئوية

---

## 📋 المدخلات (Features)

| # | الخاصية | النوع | القيم الممكنة | الوصف |
|---|---------|-------|---------------|-------|
| 1 | CreditScore | رقمي | 350–850 | الدرجة الائتمانية للعميل |
| 2 | Age | رقمي | 18–100 | عمر العميل |
| 3 | Tenure | رقمي | 0–10 | عدد سنوات التعامل مع البنك |
| 4 | Balance | رقمي | 0–300,000 | الرصيد الحالي بالدولار |
| 5 | EstimatedSalary | رقمي | 0–300,000 | الراتب السنوي التقديري |
| 6 | NumOfProducts | فئوي | 1, 2, 3, 4 | عدد منتجات البنك المشترك فيها |
| 7 | Geography | فئوي | France, Germany, Spain | دولة العميل |
| 8 | Gender | فئوي | Female, Male | نوع العميل |
| 9 | HasCrCard | ثنائي | Yes / No | هل معاه بطاقة ائتمان؟ |
| 10 | IsActiveMember | ثنائي | Yes / No | هل العميل عضو نشط؟ |

---

## 🧠 تفاصيل الموديل

### Pipeline Architecture

```
Input Data
    │
    ├── Numerical Features (StandardScaler)
    │   └── CreditScore, Age, Tenure, Balance, NumOfProducts,
    │       HasCrCard, IsActiveMember, EstimatedSalary
    │
    ├── Categorical Features (OneHotEncoder)
    │   └── Geography, Gender
    │
    └── RandomForestClassifier
        ├── n_estimators: 200
        ├── max_depth: 10
        ├── random_state: 42
        └── class_weight: balanced
```

### أداء الموديل

| المقياس | القيمة |
|---------|--------|
| **Accuracy** | 86.8% |
| **ROC-AUC** | 0.85 |
| **Precision (Churn)** | ~0.84 |
| **Recall (Churn)** | ~0.80 |
| **F1-Score (Churn)** | ~0.82 |

### البيانات

- **المصدر:** Kaggle — Bank Customer Churn Dataset
- **الحجم:** 10,000 عميل بنك أوروبي
- **نسبة الـ Churn:** ~20.4% (غير متوازنة — تم معالجتها بـ `class_weight='balanced'`)

### المعالجة المسبقة

- **StandardScaler:** توحيد الأعمدة الرقمية (متوسط = 0، انحراف معياري = 1)
- **OneHotEncoder:** تحويل الأعمدة الفئوية (Geography, Gender) إلى أعمدة ثنائية
- **Train/Test Split:** 80% تدريب، 20% اختبار مع `stratify` للحفاظ على نسبة الـ churn

---

## 🎨 لقطات الشاشة

<p align="center">
  <i>⚠️ الصور هتتحط هنا قريب</i>
</p>

---

## 🔮 التطوير المستقبلي

- [ ] إضافة SHAP/LIME لتفسير التوقعات (Explainable AI)
- [ ] Export التقرير كـ PDF
- [ ] دعم رفع ملف CSV لتحليل batch
- [ ] مقارنة بين موديلات مختلفة (XGBoost, LightGBM, Logistic Regression)
- [ ] إضافة feature importance visualization
- [ ] Deploy على Streamlit Cloud / Hugging Face Spaces
- [ ] دعم اللغة العربية في الواجهة
- [ ] Hyperparameter tuning مع GridSearchCV

---

## 📄 الترخيص

هذا المشروع مرخص تحت [MIT License](LICENSE) — تقدر تستخدمه وتعدل عليه بحرية.

---

## 👤 المطور

<p>
  <b>كيرلس صلاح فخري (Keroles Salah Fakhry)</b> — <b>KSF</b><br>
  🎓 Computer Science Student — Assiut National University<br>
  🤖 AI & Machine Learning Enthusiast
</p>

<p>
  <a href="https://keroles-sala.me/"><img src="https://img.shields.io/badge/Portfolio-keroles--sala.me-D552A3?logo=google-chrome&logoColor=white" alt="Portfolio"></a>
  <a href="https://github.com/keroles-salah"><img src="https://img.shields.io/badge/GitHub-keroles--salah-181717?logo=github&logoColor=white" alt="GitHub"></a>
  <a href="https://www.linkedin.com/in/kerolessalah05/"><img src="https://img.shields.io/badge/LinkedIn-kerolessalah05-0A66C2?logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://www.youtube.com/@kerlssalah"><img src="https://img.shields.io/badge/YouTube-@kerlssalah-FF0000?logo=youtube&logoColor=white" alt="YouTube"></a>
</p>

---

<p align="center">
  <sub>Built with ❤️ by KSF | © 2026</sub>
</p>
