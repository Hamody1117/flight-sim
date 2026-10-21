العربية

AirCore مختبر تجريبي مفتوح يعمل في المتصفح بدون تثبيت. تضع فيه طائرات ومسيّرات في سماء افتراضية، فيختبر هل تتفادى بعضها أم تتصادم، ويقارن أربع طرق للتفادي بتجارب قابلة للإعادة، ويصدّر النتائج.

ملاحظة مهمة: المشروع تعليمي وتجريبي. ليس نظام مراقبة جوية، وليس نظاماً دفاعياً، ولا تنتقل نتائجه مباشرة إلى الطيران الحقيقي.

المزايا
طائرات ومسيّرات معاً بسلوكين مختلفين: الطائرة سريعة وتدور ببطء، والمسيّرة رشيقة وتحوم.
أربعة أنماط تفادٍ يمكن التبديل بينها أثناء التشغيل:
بدون تفادٍ.
تفادٍ يعتمد على المسافة الحالية (أسلوب الحقول الكامنة).
تفادٍ تنبؤي: يتوقع أقرب اقتراب (TCPA وDCPA) ويعدّل الاتجاه مبكراً.
ORCA: التفادي المتبادل الأمثل (خوارزمية RVO2).
طرازات واقعية بمواصفات موثّقة: Cessna 172S وDJI Mavic 3 Enterprise، ودوران بمعادلة الدوران المنسّق معدل الدوران = g × tan(زاوية الميل) ÷ السرعة، ومعايير فصل حقيقية (NMAC = 500 قدم، LoWC = 2000 قدم).
عرض خطورة كل زوج: TCPA (متى أقرب اقتراب) وDCPA (كم سيكون الفاصل).
خريطة السودان ونافذة عمل بمقياس حقيقي: اختر موقعاً (عواصم الولايات ومناطق زراعية) أو الصق إحداثيات من خرائط جوجل.
سيناريوهات معيارية: وجهاً لوجه، تقاطع، مسيّرة تحوم في طريق طائرة.
وضع التجارب: مقارنة الأنماط، وأثر الازدحام، وتحليل الحساسية، ودقة التنبؤ والكشف. بذور عشوائية ثابتة، تكرارات، متوسط وانحراف معياري، وتصدير CSV.
28 اختبار تحقق آلياً تعمل بضغطة زر.
تسريع الزمن (×1 حتى ×20)، ومقياس بالمتر للعرض.
التشغيل

الملف الرئيسي واحد: index.html. افتحه بنقرتين في أي متصفح حديث. لا يلزم سيرفر ولا بناء. (تحتاج الإنترنت فقط لتحميل حدود الخريطة.)

للنشر: GitHub Pages أو Vercel أو Netlify.

كيف تستخدمه
اضغط + طائرة أو + مسيّرة، أو اختر العدد والنمط واضغط تعبئة.
اضغط على مركبة لتحديدها، ثم اضغط مكاناً لتحديد وجهتها.
بدّل نمط التفادي بزر تفادي وراقب الفرق (الخط البرتقالي: اقتراب، والأحمر: تصادم).
اختر طرازاً واقعياً من القائمتين المجاورتين (يُضبط المقياس والتسريع تلقائياً).
افتح وضع التجارب لتشغّل المقارنات، ثم تنزيل CSV.
افتح اختبارات التحقق الآلية واضغط شغّل الاختبارات.
نتائج أولية

تجربة عشوائية: 3 طائرات و8 مسيّرات بالنموذج العام، 60 ثانية، 5 بذور (1 إلى 5)، منطقة 1200×620 بكسل. المتوسطات:

النمط	تصادمات	وجهات بُلغت	أقرب مسافة (بكسل)
بدون تفادٍ	17.2	58.2	1.6
حسب المسافة	1.4	45.6	19.0
تنبؤي	0.2	44.2	26.9
ORCA	0.0	49.6	37.5
التفادي يخفض التصادمات كثيراً بثمن في الإنتاجية (عدد الوجهات المبلوغة).
في هذه الإعدادات تفوّق ORCA على النمط التنبؤي البسيط.
قياس دقة التنبؤ (بدون تفادٍ، إنذار اقتراب خلال 10 ث): الدقة نحو 79% والاستدعاء نحو 43%. فالتنبؤ الخطي يفوّت أكثر من نصف الاقترابات الفعلية لأن المركبات تغيّر اتجاهها.

هذه أرقام من تشغيل أولي، أعد تشغيل التجارب بنفسك (10 تكرارات فأكثر) وسجّل حجم المنطقة، فالأرقام تتغير بتغيّر الحجم والإعدادات.

الحدود
ثنائي الأبعاد بلا ارتفاع، وفيزياء مبسّطة (بلا رياح ولا وقود).
كل مركبة تعرف موضع غيرها بدقة كاملة (بلا أخطاء حساسات).
الأرقام نتائج داخل النموذج، وليست معدلات تصادم حقيقية.
التنبؤ خطي (سرعة واتجاه ثابتان).
في ORCA نستعمل اتجاه السرعة الناتجة فقط، لأن سرعة المركبات ثابتة وحدّ دورانها محدود.
إحداثيات المدن لمراكز المدن (± بضعة كيلومترات)، وهي للعرض فقط.
افتراضات من عندنا لا مصدر لها: أفق التنبؤ 45 ثانية للطرازات الواقعية، ونسبة الفاصل الآمن 0.79 من LoWC، والمقياس الافتراضي.
المصادر
Cessna 172S: سرعة كروز 124 عقدة (دليل معلومات Cessna 172S، عبر Plane & Pilot).
حد الدوران: إرشاد ICAO (ميل 25° أو معدل 3°/ث أيهما أقل، عبر SKYbrary)، ومعادلة الدوران المنسّق.
DJI Mavic 3 Enterprise: ورقة مواصفات DJI (ميل أقصى 30°، دوران أقصى 200°/ث، وسرعة اختبار الاستمرارية 32.4 كم/س).
NMAC وLoWC: وثائق PX4 (تطبيق ASTM F3442) ووثائق NASA/FAA.
ORCA: van den Berg وآخرون، جامعة نورث كارولاينا (مكتبة RVO2، Apache-2.0).
حدود الدول: Natural Earth (عبر حزمة world-atlas). حدود الولايات: geoBoundaries (CC BY 4.0).
المطوّر

محمد عمر أحمد محمد — مهندس برمجيات، جامعة كرري (كلية علوم الحاسوب وتقانة المعلومات).

الترخيص: MIT. انظر ملف LICENSE.

English

AirCore is an open, browser-based lab for testing collision-avoidance algorithms between aircraft and drones. No installation needed. Place aircraft and drones in a virtual sky, compare four avoidance strategies in reproducible experiments, and export the results.

Important: this is an educational and experimental model. It is not an air-traffic-control system, not a defense system, and its results do not transfer directly to real aircraft.

Features
Aircraft and drones together, with different motion models (aircraft: fast, wide turns; drones: agile, can hover).
Four avoidance modes, switchable at runtime: none; distance-based (potential-field style); predictive (time/distance of closest approach); ORCA (Optimal Reciprocal Collision Avoidance, RVO2).
Realistic profiles with documented specs: Cessna 172S and DJI Mavic 3 Enterprise, turn rate from coordinated-turn physics (ω = g·tan(bank) / V), and real separation standards (NMAC = 500 ft, LoWC = 2000 ft).
Per-pair risk readout: TCPA and DCPA.
Sudan map and a real-scale work window: choose a location (state capitals, agricultural areas) or paste coordinates from Google Maps.
Standard scenarios: head-on, crossing, hovering drone in an aircraft's path.
Experiment mode: mode comparison, density sweep, sensitivity analysis, prediction/alert accuracy. Fixed random seeds, repeats, mean ± SD, CSV export.
28 automated verification tests at the press of a button.
Time acceleration (×1 to ×20) and a metre scale for display.
Run

A single file: index.html. Open it in any modern browser; no server or build step. (Internet is only needed to load map boundaries.) Deploy with GitHub Pages, Vercel, or Netlify.

Preliminary results

Random experiment: 3 aircraft + 8 drones (generic model), 60 s, 5 seeds (1–5), 1200×620 px area. Means:

Mode	Collisions	Waypoints reached	Closest approach (px)
No avoidance	17.2	58.2	1.6
Distance-based	1.4	45.6	19.0
Predictive	0.2	44.2	26.9
ORCA	0.0	49.6	37.5
Avoidance cuts collisions sharply at a cost in throughput.
In this setup ORCA outperformed the simple predictive mode.
Prediction accuracy (no avoidance, 10 s alert horizon): precision ≈ 79%, recall ≈ 43%. Linear extrapolation misses over half of actual approaches because vehicles change heading.

These are first-run numbers. Re-run the experiments yourself (10+ repeats) and record the area size, since results depend on it.

Limitations
2D only (no altitude); simplified physics (no wind, no fuel).
Every vehicle knows others' exact positions (no sensor error).
Results hold inside the model; they are not real collision rates.
Linear prediction (constant speed and heading).
ORCA is adapted: only the direction of the computed velocity is used, since vehicles fly at constant speed with limited turn rate.
City coordinates are approximate (± a few km) and for display only.
Our own assumptions (no source): 45 s look-ahead for realistic profiles, safe-distance ratio 0.79 of LoWC, default scale.
Sources
Cessna 172S: cruise 124 kt (Cessna 172S Information Manual, via Plane & Pilot).
Turn limits: ICAO guidance (25° bank or rate-one, whichever is less; via SKYbrary) and the coordinated-turn equation.
DJI Mavic 3 Enterprise: DJI spec sheet (30° max tilt, 200°/s max angular velocity, endurance test speed 32.4 km/h).
NMAC / LoWC: PX4 documentation (ASTM F3442 implementation) and NASA/FAA documents.
ORCA: van den Berg et al., UNC (RVO2 library, Apache-2.0).
Boundaries: Natural Earth (via world-atlas); state boundaries: geoBoundaries (CC BY 4.0).
Author

Mohamed Omar Ahmed Mohamed — software engineer, Karary University (Faculty of Computer Science and Information Technology).

License: MIT. See LICENSE.
