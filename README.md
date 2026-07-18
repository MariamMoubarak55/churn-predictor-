# Bank Churn Predictor

تطبيق ويب لتوقع احتمالية مغادرة عملاء البنك (Customer Churn Prediction).

## المتطلبات

- Python 3.10+
- pip

## التثبيت والتشغيل

```bash
# 1. استنسخ المشروع أو فك الضغط

# 2. ثبت المكتبات المطلوبة
pip install -r requirements.txt

# 3. شغّل التطبيق
streamlit run app.py

# 4. افتح المتصفح على http://localhost:8501
```

## الملفات

| الملف | الوصف |
|-------|-------|
| `app.py` | تطبيق Streamlit — الواجهة الرسومية |
| `bank_churn_model_full.pkl` | الموديل المدرب (Random Forest مع Pipeline) |
| `requirements.txt` | المكتبات المطلوبة |
| `README.md` | هذا الملف |

## استخدام التطبيق

1. ادخل بيانات العميل في الحقول
2. اضغط على زر "توقع هل هيمشي؟"
3. شوف النتيجة — هل العميل متوقع يمشي ولا لأ، والاحتمالية بالنسبة المئوية

## الموديل

- **النوع**: Random Forest Classifier
- **البيانات**: 10,000 عميل بنك أوروبي
- **الدقة**: ~86.8% على بيانات الاختبار
- **ROC-AUC**: ~0.85

## ملاحظات

الموديل مدرب باستخدام Pipeline (Scikit-learn) يحتوي على:
- StandardScaler للأعمدة الرقمية
- OneHotEncoder للأعمدة النصية (Geography, Gender)
- RandomForestClassifier (200 شجرة، max_depth=10)

البيانات المدخلة للنموذج يجب أن تكون بنفس تنسيق بيانات التدريب الأصلية.
