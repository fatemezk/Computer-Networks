# آشنایی با الگوریتم های مسیریابی شبکه

--------------------------------------------------------------------------------------------------------
کلاسNetWork:


![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/c7d01b0d-fe17-4664-8aed-afe42ec3ba26)

این کلاس یک interface کلی برای کار با شبکه ارائه میدهد که از آنها برای اجرای دستورات پروژه استفاده میشود.

1-تابع make topology:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/5141ed28-7696-4ed4-b9b3-e14e1255ea44)

در این تابع که از آن برای اجرای دستور topology استفاده میشود؛ گراف شبکه به صورت یک آرایه ی دو بعدی link ذخیره میشود. به اینصورت که مقدار link[i][j] در واقع به وزن لینک میان نود i,j اشاره دارد. اگر این مقدار برابر -1 باشد یعنی میان دو نود، لینکی وجود ندارد.بنابراین در ابتدا مقدار این آرایه را برابر -1 قرار میدهیم. سپس با مقادیر داده شده، توپولوژی شبکه را میسازیم. از آن جایی که نودها از 1تا n شماره گذاری شده اند، تعداد نودها برابر با بزرگترین شماره نود دریافتی میباشد که در حلقه ی while آپدیت کرده ایم. این تابع در صورتیکه نودهای مبدا و مقصد آن یکسان باشند، پیغام خطای مناسبی را چاپ میکند.نمونه ای از اجرای برنامه:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/3294d6b1-c58e-4ff7-983a-84395a9117d0)


برای شکاندن رشته های دریافتی به صورت مبدا و مقصد و وزن، از تابع splitArgs استفاده کرده ابم که نحوه ی کار آن ساده و واضح است.

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/43c75895-2a0e-4589-9e85-58f529a8e5d6)

2-تابع show topology:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/9c60164d-ca14-4551-ae7a-cec3a6efcb2b)


در این تابع که برای اجرای دستور show استفاده میشود؛با استفاده از ماتریس مجاورت و اقداماتی که برای زیبا چاپ شدن خروجی انجام شده اند، توپولوژی شبکه نمایش داده میشود.نمونه ای از اجرای برنامه با topology ذکر شده در صورت پروژه:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/da2f47a3-16f2-4ee5-beb3-e8ddf8920e60)

3-تابع lsrp:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/73708042-835d-42ba-b394-5fa02563cce2)

از این تابع برای اجرای دستور lsrp با یک مبدا استفاده میشود. الگوریتم link state همان الگوریتم dijkestra برای یافتن کوتاه ترین مسیر میباشد.کارکرد این الگوریتم به صورت زیر است:

از سه آرایه استفاده میکنیم. اولی visited است که نشان میدهد آن نود بررسی شده است یا نه و مقدار اولیه ی آن برای همه ی نودها false است.دومی distance که نشان دهنده ی فاصله از نود مبدا و در آخر هم آرایه ی parent برای نگهداری نود قبلی که در کوتاهترین مسیر از مبدا به نود فعلی از آن عبور کرده ایم. فاصله ی همه ی نود ها از مبدا را در ابتدا برابر با یک عدد بسیار بزرگ در نظر میگیریم.

الگوریتم در هرمرحله نزدیکترین نود بررسی نشده به مبدا را انتخاب کرده و فاصله ی مبدا را تا همسایه های خود محاسبه میکند. این فاصله همان فاصله ی نزدیکترین نود تا مبدا به علاوه ی فاصله ی لینک میان آن و نود همسایه اش میباشد. در صورتیکه مقدار بدست آمده از فاصله ی فعلی که در distance ذخیره شده،کمتر باشد یعنی مسیر کوتاهتری از مبدا به آن نود پیدا شده است و باید parent آن را به نود فعلی مورد بررسی و فاصله اش را با فاصله ی جدید بدست آمده جایگزین کنیم.

در نهایت distance مقدار کوتاهترین مسیر از مبدا به هرنود و parent نود قبلی هر نود در مسیر را نشان میدهند.

برای محاسبه ی زمان همگرایی از مقایسه ی زمان در ابتدا و انتهای تابع استفاده شده است.نتیجه برای نود 1:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/ead6586e-97d1-4dda-97bc-f482388bd3be)

تابع printIteration:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/7e18f349-d62b-4872-a358-afe628970209)

برای نمایش نتایج در هر پیمایش از تابع printIteration استفاده شده است.
این تابع با استفاده از آرایه های parent , distance اطلاعات پیشمایش را در فرمت خواسته شده چاپ میکند.

تابع printPaths:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/087295f9-68bd-4984-a2a8-92a8ed4977e5)

برای نمایش جدول نهایی از تابع printPaths استفاده شده است.
این تابع با استفاده از اطلاعات iteration , parent نتایج کلی حاصل از الگوریتم lsrp را در فرمت خواسته شده نشان میدهد.در این تابع برای هر مسیر، مبدا و مقصد آن،کمترین هزینه و همچنین گام های مسیر نمایش داده میشوند. برای نمایش مسیر از تابع بازگشتی printPath استفاده شده است.

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/c3a7d4eb-ee14-4fce-aae5-69a0d62b1339)

این تابع در هر بار اجرا با parent نود فعلی فراخوانی شده و این کار را تا رسیدن به نود مبدا ادامه میدهد که parent آن مقدار -1 دارد.حالا مسیر را در بازگشت از مبدا به سمت مقصد چاپ میکند.

تابع lsrpAll:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/7ddf96fb-e29e-4862-ab47-5aed4ef9ffee)

در صورتی که دستور lsrp بدون آرگومان فراخوانی شود؛لازم است نتایج تابع lsrp به ازای تمامی نودها چاپ شود.بنابراین در این تابع تمامی نودهای شبکه یک بار به عنوان مبدا در نظر گرفته میشوند و الگوریتم برای آنها اجرا خواهد شد.همچنین برای محاسبه ی زمان کلی اجرای الگوریتم به ازای تمامی نودها در ابتدا و انتهای این تابع نیز زمان حال را محاسبه و ذخیره میکنیم و از هم کم میکنیم.(در این مرحله به منظور صرفنظر از زمان لازم برای چاپ نتایج، از نتایج جداول و.. صرفنظر کرده و با کامنت کردن آنها به صورت موقتی،تنها زمان خالص لازم برای اجرای الگوریتم را محاسبه کرده ایم)

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/6e1735e9-777e-4d1e-a227-c64209b2762f)

4-تابع dvrp:
![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/6047cbc5-2775-4c96-8ce1-62750df6dee0)

از این تابع برای اجرای دستور dvrp با یک مبدا استفاده میشود.الگوریتم distance vector در واقع همان الگوریتم bellman-ford برای یافتن کوتاهترین مسیر است. کارکرد این الگوریتم به صورت زیر است:

از دو آرایه ی distance و parent استفاده میکنیم. که مانند الگوریتم قبلی،distance برای ذخیره ی فاصله از مبدا استفاده شده و مقدار اولیه ی آن برای تمامی نودها برابر با عددی بسیار بزرگ است. parent نیز برای نگهداشتن نود قبلی که در کوتاهترین مسیر از مبدا به نود فعلی از آن عبور کرده ایم، استفاده میشود.

سپس الگوریتم با n بار چرخش بر روی تمامی یالها در صورتی که مسیر کوتاهتری از مبدا به یک راس پیدا کند، آن را با مسیر قبلی جایگزین میکند. به این صورت که parent و فاصله را با مقادیر جدید تغییر میدهد.

در پایان اجرای این الگوریتم،distance نشان دهنده ی کوتاهترین مسیر از مبدا و parent نشان دهنده ی نود قبلی آن در این مسیر خواهد بود.

در این تابع نیز برای محاسبه ی زمان همگرایی الگوریتم، در ابتدا و انتهای تابع زمان حال را ذخیره و از هم کم میکنیم.نتیجه ی اجرای این الگوریتم از مبدا 1 به صورت زیر است:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/277bed87-1606-43a4-9a2a-593e9a682d77)

تابع printTable:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/ce611a28-cd86-4da6-b9d7-18b31dca5967)

برای نمایش نتایج نهایی اجرای الگوریتم از این تابع استفاده شده است.این تابع با استفاده از distance , parent و نود مبدا، نتایج فواصل نهایی را چاپ میکند.در این تابع نیز از تابع printPath که پیشتر به توضیح آن پرداختیم استفاده میشود.در صورتیکه راس میدا و مقصد یکسان باشند دیگر نیازی به فراخوانی این تابع نخواهیم داشت.همچنین برای محاسبه ی next hop از تابع جداگانه ی دیگری استفاده میکند.

تابع getNextHop:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/352cb856-ff00-4665-94a4-ff53f8865174)

این تابع با استفاده از parent اولین پرش بعد از راس مبدا را محاسبه کرده و شماره ی آن را برمیگرداند.

تایع dvrpAll:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/2c8d577c-dd55-432b-a14c-1fdf56565fe2)

در صورتی که دستور dvrp بدون آرگومان فراخوانی شود؛لازم است نتایج تابع dvrp به ازای تمامی نودها چاپ شود.بنابراین در این تابع تمامی نودهای شبکه یک بار به عنوان مبدا در نظر گرفته میشوند و الگوریتم برای آنها اجرا خواهد شد.همچنین برای محاسبه ی زمان کلی اجرای الگوریتم به ازای تمامی نودها در ابتدا و انتهای این تابع نیز زمان حال را محاسبه و ذخیره میکنیم و از هم کم میکنیم.(در این مرحله به منظور صرفنظر از زمان لازم برای چاپ نتایج، از نتایج جداول و.. صرفنظر کرده و با کامنت کردن آنها به صورت موقتی،تنها زمان خالص لازم برای اجرای الگوریتم را محاسبه کرده ایم)

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/e069a90f-ebaa-4b19-9f70-8e8cce4480c1)

5-تابع modifyLink:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/38b99122-f134-4514-b157-93488cfed6df)

در این تابع که برای اجرای دستور modify میباشد؛ ابتدا بررسی میکنیم که نود مبدا و مقصد یکسان نباشند و در صورت یکسان بودن پیغام مناسب این خطا را نمایش میدهیم. در غیر این صورت هزینه ی لینک مورد نظر را تغییر داده یا لینکی با هزینه ی وارد شده ایجاد میکنیم.همانطور که در تابع makeTopology توضیح داده شد برای این کار تنها لازم است مقادیر خانه های آرایه ی دو بعدی links را برای خانه های مبدا و مقصد تغییر دهیم.همچنین برای شکستن ورودی به نودهای مبدا و مقصد و مقدار هزینه، از تابع splitArgs استفاده میکنیم که پیشتر توضیح داده شد.نتیجه ی اجرای این دستور به شکل زیر است:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/0b201847-e778-4252-b079-f25bf4d5d419)

6-تابع removeLink:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/f193cacf-d355-42b2-ae4f-701c6581994d)

در این تابع که برای اجرای دستور remove از آن استفاده میشود؛ ابتدا بررسی میکنیم که آیا لینک وارد شده موجود است.(عدم وجود لینک میتواند به دلیل نبود یال و یا به دلیل عدم وجود یکی از نودهای گفته شده در شبکه باشد)اگر موجود نباشد پیغام مناسب را نمایش میدهیم. در غیر این صورت مقدار خانه های مربوط به این لینک را در آرایه ی دو بعدی links برابر با -1 قرار میدهیم که نشان دهنده ی عدم وجود لینک میان دو نود است.نتیجه ی اجرای این دستور به شکل زیر است:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/45e553a6-7036-4ca2-bae4-d13cec9f220f)

7-تایع handleCommands:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/655dc423-8327-4f82-8120-872214b518a2)

این تابع برای گرفتن دستورات ورودی و تشخیص توابع مربوط به آن هاست.پس از تقسیم ورودی به دو بخش command و argoman، تابع مورد نظر را با آرگومان های مربوطه فراخوانی میکند.این تابع در صورتیکه دستورات dvrp,lsrp بدون آرگومان وارد شده باشند، تابع های all مربوط به  آنها را فراخوانی کرده و در غیر این صورت توابع اصلی مربوطه را فراخوانی میکند. در صورتیکه دستور وارد شده معتبر نباشد، پیغام خطای مناسب را چاپ میکند.

# مقایسه ی نتایج:

برای الگوریتم های dvrp,lsrp نتایج مسیریابی از نود 1 بعنوان مبدا به صورت زیر است:

lsrp:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/f0043aa7-ab6b-4f35-8727-bd30672b6430)

dvrp:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/a56de22c-ed0c-4f82-b1a0-83bb9c61795c)

همانطور که مشاهده میشود کوتاهترین مسیر برای هردوی آنها یکسان و بهینه میباشد.


برای الگوریتم های lsrp , dvrp نتایج پس از حذف مسیر 10-4 به این صورت است:

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/04d6fe66-fe91-4eb4-9d93-5c0d7264d783)

![image](https://github.com/fatemezk/CN_CHomworks_3/assets/93648284/0e1bdad4-3771-47dc-9b7a-4af6a2be970b)

از آنجایی که پیچیدگی زمانی الگوریتم bellman-ford از dijkestra بیشتر است پس همانطور که در نتایج بالا نیز مشخص است، این الگوریتم زمان اجرای بیشتری خواهد داشت.




















