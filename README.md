🏠 California Housing Price Prediction

پیش‌بینی قیمت مسکن کالیفرنیا با استفاده از الگوریتم‌های رگرسیون و پردازش داده‌های واقعی سرشماری.

📌 The project summary

· هدف: پیش‌بینی median_house_value با داده‌های ۲۰,۶۴۰ بلوک مسکونی کالیفرنیا
· ابزارها: Python, Pandas, Scikit-learn, Matplotlib, Seaborn
· فرایند:
  · جای‌گذاری مقادیر گمشده با KNN Imputer
  · شناسایی و محدودسازی نقاط پرت (IQR Capping)
  · مقیاس‌سازی با StandardScaler
  · مقایسه‌ی ۶ مدل رگرسیونی


🏆 Best model

· مدل: Random Forest
· R²: 0.8306
· RMSE: 46,532
· MAE: 31,295


📈 Evaluation

مدل‌های مبتنی بر درخت (Random Forest) به‌طور قابل‌توجهی از مدل‌های خطی (R² ≈ 0.65) بهتر عمل کردند که نشان‌دهنده‌ی وجود روابط غیرخطی در داده‌های مسکن است.