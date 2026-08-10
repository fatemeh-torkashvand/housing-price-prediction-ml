پیش‌بینی قیمت مسکن – پروژه‌ی ماشین‌لرنینگ

یک رگرسیون برای پیش‌بینی قیمت متوسط خانه‌ها در مناطق کالیفرنیا، بر اساس دیتاست California Housing. این پروژه شامل پاک‌سازی داده، برخورد با داده‌های پرت، ارزیابی مدل‌ها، تنظیم هایپرپارامتر و ذخیره‌سازی مدل نهایی است.
_دیتاست

· منبع: فایل housing.csv
· هدف (Target): median_house_value
· تعداد نمونه: ۲۰,۶۴۰ رکورد با ۹ ویژگی (شامل طول و عرض جغرافیایی)


_پیش‌ پردازش داده

· مقادیر گم‌شده – با استفاده از KNNImputer (با ۵ همسایه) برای ستون total_bedrooms پر شده‌اند.
· مدیریت داده‌های پرت – با روش IQR، سه ستون زیر کیپ (cap) شده‌اند:
  · median_house_value
  · median_income
  · housing_median_age
  · scaling –

_ مدل‌های ارزیابی‌شده

همه‌ی مدل‌ها با اعتبارسنجی متقابل ۵‑لایه روی مجموعه‌ی آموزش ارزیابی شدند:

1.Linear Regression
2.Rodge Regression
3.Lasso Regressin
4.Decision Tree
5. Random Forest
6. (KNN)


_ تنظیم هیپرپارامتر

دو مدل برتر با RandomizedSearchCV بهینه‌سازی شدند:

· Random Forest – بهترین پارامترها:
    n_estimators=150, min_samples_split=5, min_samples_leaf=2, max_depth=None
· KNN – بهترین پارامترها:
    n_neighbors=7, weights='distance', p=1 

_ عملکرد نهایی روی مجموعه‌ی آزمون

مدل ضریب تعیین (R²)
جنگل تصادفی ۰٫۸۱۴۰
KNN ۰٫۷۲۰۷

تمام نتایج اعتبارسنجی متقابل (شامل RMSE و MAE) داخل نوت‌بوک ثبت شده‌اند.

_ مدل‌های ذخیره‌شده

پس از بهینه‌سازی، هر دو مدل نهایی با joblib ذخیره شده‌اند:

· best_rf_model.pkl
· best_knn_model.pkl