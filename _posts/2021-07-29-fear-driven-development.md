---
title: صناعة السوفتوير للسوفتوير انجينيرز
image: /images/IMG_20210605_125650.webp
---

صناعة السوفتوير اللى العملاء بتوعه نفسهم سوفتوير انجينيرز كل سنة بيزدهر عن السنة اللى قبلها، لأسباب كتير منها ان الستارت ابس عاوزة تطلع بسرعة time to market او قلة خبرة الديفلوبرز فى ستارت ابس كتير، او ان الحاجة هتاخد وقت كبير، او الوهم ان خبرة الديفلوبرز قليلة على الفيتشر او الوهم ان الحاجة هتاخد وقت كبير وده الجرح اللى عاوز افتحه وادوس عليه المرة دي.
فيه سوفتوير كتير الديفلوبرز بيستخدموه اليومين دول وبيتدفع قدامه فلوس بالهبل، بيزود تعقيد الأنظمة، وبيبطأ الأنظمة دي ومنها اللى بيأثر على تجربة المستخدم من سرعة وحجم الابليكيشن وحتى مشاكل فى الخصوصية.
مثال على ده:

- ابليكيشنز تتبع المستخدم فى الويب ابليكيشنز، مش محتاج اقول انها وباء على الويب وحاجة محتاجة يتولع فيها بجاز وسخ.
- ابليكيشنز الLogging, error reporting, monitoring اللى ماشية بنظام الSaaS، اللى معظم الفيتشرز فيها مابيبقاش الواحد محتاجها اصلا بس اهي جاية مع السوفتوير ويللا نستخدمها، والموضوع بينتهي انك حاطط بتاع 50 dependency علشان البهوات اللى عاملين ال SDK عاملينها dependency على الكود بتاعهم.
- ابليكيشنز الauthentication مع 500 provider تاني واللى انت يمكن محتاج منهم مثلا 3 او ساعات 1.
- ابليكيشنز البيروقراطية زي Jira وامثاله اللى بقى التعامل معاهم فى حد ذاته شغلانة وبقى مضيعة للوقت لمعظم الناس اللى محتاجين حاجة بسيطة خالص لتيم كل اللى فيه 4 بنى ادمين مثلا.
- السيستيمز ابليكيشنز الاوفر انجينيرد وماتناسبش معظم استخدامات الناس العادية زي kubernetes او rabbitMQ او kafka

الامثلة كتير ومتأكد ان كل ديفلوبر بيستخدم على ابليكيشن واحد على الأقل من اللى فوق دي، وحياته بتضيع قدام عينيه فى الintegrations لأيام مع ان ممكن اللى محتاجه يخلص فى ساعتين وشوية تنظيم وتحديد للي محتاجه.

اكبر سبب من وجهة نظرى اللى مالهاش اي لازمة هو الخوف، الديفلوبرز فى خوف مستمر بيتدخل تقريبا فى كل قرارات التكنولوجيز، رغم ان كل الناس بتدعي ان قرارتهم منطقية ومبنية على مميزات وعيوب ومناقشات واخد ورد وفوق وتحت وهنا وهناك وكل الكلام الجميل ده، بس فى الاخر الroot cause هو الخوف، مثال على كده:

- استخدام ابليكيشنز زي kafka تحته خوف ان اي ابليكيشن انت هتكتبه علشان يعمل بس اللى انت محتاجه مش هيكون يعني احسن من حاجة مكتوبة فى linkedin بعتاولة الانجينيرنج. وبما انه اوبن سورس يبقى اكيد ناس كتير بتحسنه.
- استخدام error reporting زي sentry تحته خوف مشابه ان اكيد احسن من انني اعمل log للايرورز فى اي سيستيم انا كاتبه او حتي فى files على الديسك
- استخدام حاجة زي jira تحته خوف من العشوائية اللى ممكن تنتج عن حاجات ابسط بكتير زي حتى ملف على google docs، لأن هنعمل ايه لو محتاجين فيتشر الcustom fields أوعاوزين نعمل سيرش على  حاجة من 3 سنين ومش لاقيينها؟
- استخدام حاجة زي kubernetes وراه خوف ان managing السيرفرز حاجة صعبة وهنعمل ايه لو عندنا 20 سيرفر ولا 30 وعاوزين نقسم الريسورسيز؟ وان الديفلوبرز عندي مايقدروش يكتبوا حاجة بتعمل كده او على الاقل بتحقق اللى محتاجينه.

معظم الخوف بيتركز فى قلة الثقة فى النفس والتيم انهم يعملوا حاجة تقضى الغرض وان اكيد حد غريب ماعرفوش على الانترنت بيشتغل فى linkedin او فيسبوك هيكتب حاجة احسن للسيستيم بتاعي من اللى انا هكتبه للسيستيم، انا اللى عارف احتياجاتي والسيستيم اللى ببنيه عارف اقل من اللى بيبني سيستيم generic على الطرف التاني من الكوكب.

طريقة التفكير دي مش بس بتنتج انظمة معقدة وبطئية وتحكم الديفلوبر فيها صفر (لأن 90% من الكود مايعرفش عنه حاجة) ، لا ده بيبقى سيستم هش وفى اي وقت اي حاجة من دي ممكن تولع وماتعرفش تطفيها او تقع وماتعرفش تقومها زي ما كان شركات كبيرة مستخدمه حاجة زي fastly ولما وقعوا وقعوا نص الانترنت معاهم.

مشكلة تانية فى التفكير ده ان الداتا بتاعة المستخدمين بتعدي فى كود انت ماقريتوش وماتقنعنيش انك قعدت تقرا كل سيستيم اوبن سورس استخدمته، او SDK استخدمتها، ممكن الكود ده وانت مش واخد بالك يسرق اي حاجة من الداتا دي او يكون ليهم privacy policy بتسمح بمشاركة المعلومات اللى انت طبعا ماقريتهاش، فوانت مش واخد بالك الكود ده حرفيا ممكن يقلعك هدومك ويخسرك شغلك نفسه.

مشكلة كمان الطريقة دي انها بتقتل اي فرصة للأبداع، لأن كل لما تقابل حاجة المفروض تعملها بتشك فى نفسك وتروح تدور على شركة عاملاها علشان تستخدمها وخلاص، بنفس المنطق ده كان المفروض الناس فى linkedin يروحوا يستخدموا اي حاجة موجودة بدل مايكتبوا kafka او جوجل راحت تستخدم اي سيستيم عاملاه شركة تانية بدل مايكتبوا borg.

فى رأيى ان طريقة كتابة السوفتوير واخدة منحى اننا نجمع شوية components مكتوبة من third parties وتكتب كود يوصلهم ببعض دي بتقتل الديفلوبرز وبتحولهم لgrunts، الطريقة اللى شايفها احسن هي growing software ، بالتدريج بنبني اللى محتاجينه بحيث يحل المشكلة اللى عندنا دلوقتي ويكون مكتوب كويس بحيث يسمح بتعديلات فى المستقبل، لكن فكرة اننا نبني السوفتوير زي العمارة كده ولما يكمل ابقى اسكنه واجيب لكل دور مقاول شكل ومتصممة من معمارى مختلف مش هيكون ليها رجلين تمشيها لفترة طويلة، الكود اللى ماكتبتوش بنفسك كود مش هتعرف تdebug بنفسك ولا تتحمل مسئوليته وبالتالى السيستيم كله بقى مسئولية حد تاني غيرك ولا شوفته ولا شافك ولا بيشتغل فى نفس المكان ولا مهتم اصلا انت بتعمل ايه.

الشركات اللى بتقدم السوفتوير المذكور سابقا عارفين كويس الهشاشة اللى عايش فيها الديفلوبرز طول الوقت وانهم دايما عندهم الimposter syndrom دي والماركتينج بتاعهم بيدوس قوي على النقطة دي لأن دي اللى بتخلق الأحتياج اللى بيخليك تفتح محفظة شركتك وتدفع لهم اشتراك شهرى مقابل خدمتهم. بس المشكلة بقى ان قبل مابتاخد بالك بتبقى دافع ل 30 شركة علشان 30 خدمة مختلفة، مع كل خدمة السيستيم بتاعك بقى orders of magnitude اعقد وابطأ وهش وبيسرب داتا العملاء زي قربة مخرومة 100 خرم