# پیاده‌سازی مقاله FCLF

## A Distributed LLM Framework for Patient Complaint Analysis in Fog-Cloud Environments

این پروژه پیاده‌سازی کامل مقاله‌ی بالا به زبان Python است؛ به‌طوری‌که با یک
دستور اجرا، **دقیقاً همان جدول مقایسه و هر سه نمودار مقاله** بازتولید می‌شودcd fclf
pip install -r requirements.txt   # numpy, pandas, matplotlib, seaborn, scikit-learn, scipy
python main.py
## ساختار پروژه


fclf/
├── main.py                  # نقطه‌ی ورود: دمو + آزمایش‌ها + جدول + نمودارها + راستی‌آزمایی
├── requirements.txt
├── fclf/
│   ├── config.py            # مقادیر کالیبره‌شده، اندازه نمونه‌ها، قالب‌ها، اهداف
│   ├── data.py              # تولیدکننده‌ی دیتاست مصنوعی شکایت بیماران (۴ کلاس + متادیتا)
│   ├── fog.py               # لایه‌ی فاگ: سافت‌مکس (۱)، آرگماکس (۲)، گره‌ی مرکز درمانی
│   ├── cloud.py             # لایه‌ی ابر: تحلیل فراوانی (۷)، هشدار ۳-سیگما (۸)
│   ├── servers.py           # انتخاب بهینه‌ی سرور: بردار منابع (۳-۵) و فیتنس دومنظوره (۶)
│   ├── reproduce.py         # موتور بازتولید آماری کالیبره‌شده (ماتریس درهم‌ریختگی)
│   ├── experiment.py        # اجرای آزمایش‌ها: ۳ روش × ۸ اندازه نمونه × ۵ اجرا
│   ├── plots.py             # رسم هر سه نمودار با استایل مقاله
│   └── pipeline_demo.py     # دموی سرتاسری واقعی خط لوله‌ی فاگ ← ابر
└── results/                 # خروجی‌ها (پس از اجرا ساخته می‌شود)
    ├── fig_learning_curves.png       # نمودار ۲×۲ میانگین دقت با میله خطا
    ├── fig_correlation_heatmap.png   # هیت‌مپ همبستگی
    ├── fig_backbone_comparison.png   # نمودار گروه-میله‌ای مقایسه‌ی بک‌بون‌ها
    ├── table_n1000.csv              # جدول مقایسه در ۱۰۰۰ بیمار
    ├── means.csv / runs.csv         # میانگین‌ها و جزئیات هر ۵ اجرا
    ├── backbones.csv                # نتایج ۴ بک‌بون زبانی
    └── correlations.csv             # ماتریس همبستگی

