# car and lincense plate detection project

### description(in persian)
<div dir="rtl">
<h4>مقدمه</h4>
در این پروژه از دو مدل YOLOv5 و YOLO NAS برای تشخیص خودرو و پلاک خودرو در ویدیو است.
از YOLO NAS، که بر پایه ی ساختار YOLO است برای تشخیص خودرو استفاده شده است. به لطف کلاس و وزن های از پیش train شده بر روی دیتاست COCO، تشخیص خودرو با YOLO NAS کار آسانی خواهد بود. از طرفی، مدل YOLOv5، با استفاده از یک custom dataset پلاک های خودرو از صفر train شده است.

 <h4>بررسی مدل</h4>
ساختار (YOLO(you only look once یک سیستم تشخیص اشیا است که یک عکس را به عنوان ورودی می گیرد و آن را به یک grid تقسیم بندی می کند. هر گرید سل، bounding box ها و درصد احتمال کلاس ها را پیش بینی می کند.
YOLO از یک شبکه ی عصبی برای پیش بینی bounding box ها و درصد احتمال کلاس ها به صورت همزمان استفاده می کند.
 
![0_WUpMWzNu_ymDyHPp](https://github.com/dev-parsa/object-detection/assets/105069707/32dcd8b7-5627-45b4-b9e3-b9dd4a7a971c)
 
 <h4>چه چیزی YOLO را برای تشخیص شی جذابتر از دیگر مدل ها می کند؟</h4>
YOLO بسیار سریع است. شاید سریع بودن این مدل یکی از بزرگ ترین مزیت های آن باشد. در YOLO تنها یک شبکه عصبی وجود دارد که خیلی ساده به آن ورودی تصویر داده می‌شود تا شبکه پیش‌بینی‌های تشخیص اشیا را به ما نشان دهد. سرعت YOLO باعث شده که در اپلیکیشن های real-time هم از آن بهره گرفته شود

YOLO برای پیش‌بینی تشخیص، به صورت کلی (Global) به تصویر نگاه می‌کند. برخلاف تکنیک‌های پنجره‌های لغزان (sliding window) و پروپوزال، YOLO به کل تصویر نگاه می‌کند.
  <h4>تشخیص پلاک خودرو</h4>
برای تشخیص پلاک خودرو در ویدیو، برای train مدل و fine tune کردن مدل yolov5 از یک دیتاست car license plate detection از سایت kaggle استفاده شده است. این دیتاست تقریبا دارای 400 عکس به همراه annotation آنها است. Yolov5 از فرمت txt خاصی استفاده می کند به همین دلیل باید فایل های xml را به فرمت txt  مورد قبول yolo تبدیل کنیم.
برای آموزش به مدل، batch به اندازه 32، yolov5 large، image size 320 و 100 تا epoch در نظر گرفنه شده است.
همچنین برای سرعت دادن به مرحله ی آموزش، از GPU بهره گرفته شده است.
سایر توضیحات در مورد fine tuning مدل داخل فایل notebook وجود دارد.
برخی از Metric های بدست آمده بصورت زیر است.

  ![results](https://github.com/dev-parsa/object-detection/assets/105069707/b0ca7aa9-db12-4629-adce-4aaee33b345b)

  ![labels](https://github.com/dev-parsa/object-detection/assets/105069707/14b6e7b9-0a6d-45b4-8261-a718b20e3ad4)

  <h4>تشخیص خودرو</h4>
 برای تشخیص خودرو از مدل YOLO NAS استفاده شده است. از آنجایی یکی از 80 کلاس از پیش تعریف شده ی coco ماشین است و YOLO NAS قابلیت استفاده از pretrained weights را در اختیار ما قرار داده است، نیازی به fine tune کردن مدل وجود ندارد. 
برای detect خودرو در ویدیو از مدل YOLO NAS large استفاده شده است.

  

</div>
