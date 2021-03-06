---
title: Threads
localeTitle: الخيوط
---
## الخيوط

تسلسل من تعليمات البرنامج المعطاة لنظام التشغيل للتنفيذ. وهو أصغر تسلسل متزامن يمكن تنفيذه. عندما تكون متزامنًا ، تكون التعليمات في سلسلة محادثات خطية وتنفّذ واحدة تلو الأخرى. إذا كان البرنامج يحتوي على عدة مؤشرات ترابط ، يمكن أن يكون البرنامج ككل غير متزامن في أن مؤشرات الترابط هذه تقوم بتنفيذ التعليمات الخاصة بها بشكل مستقل عن بعضها (في نفس الوقت).

مؤشر الترابط هو تجريد تستخدمه أنظمة التشغيل لتمثيل وحدة المعالجة المركزية للبرامج. لا يوجد مفهوم حقيقي للخيوط في كود الآلة أو لغات التجميع.

المواضيع هي وسيلة في البرمجة لأداء مهام متعددة في نفس الوقت.

التمييز الشائع الذي يجب على المرء القيام به هو الفرق بين الخيوط والعمليات. الخيط هو طفل من العملية إذا جاز التعبير.  
قد يكون هناك أي عدد من خيوط الطفل في سياق العملية. يمكن أن تزيد مؤشرات الترابط من سرعة تنفيذ البرنامج ، عن طريق زيادة النسبة المئوية لوحدة المعالجة المركزية المستخدمة في المهمة.  
لاحظ أن زيادة عدد مؤشرات الترابط في البرنامج بشكل كبير يمكن أن يكون مكثفًا على وحدة المعالجة المركزية ، وإذا تم استخدام 100٪ من وحدة المعالجة المركزية ، فلن يكون لمؤشرات الترابط تأثير على سرعة التنفيذ.

![خيوط داخل رسم بياني لعملية](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Multithreaded_process.svg/440px-Multithreaded_process.svg.png)

لنفترض أن لديك برامج متعددة مفتوحة - يتم تمثيل مشاركة كل برنامج من وقت وحدة المعالجة المركزية بواحد أو أكثر من سلاسل العمليات المرتبطة بهذا البرنامج. عندما يقرر برنامج **جدولة** نظام التشغيل أنه تشغيل البرنامج A ، يقوم نظام التشغيل بتغذية (أو أن يكون أكثر دقة ، تعدد الإرسال) تعليمات في مؤشر ترابط Program A إلى وحدة المعالجة المركزية ، والتي تقوم بعد ذلك بتشغيل هذه الإرشادات.

يتكون مؤشر الترابط لبرنامج معين من بعض أو كل التعليمات المجمعة لهذا البرنامج ، بالإضافة إلى بعض المعلومات المطلوبة لوحدة المعالجة المركزية لتنفيذ هذه الإرشادات.

يعد **Multithreading** مفهوم برمجة حيث ينتج برنامج عدة مؤشرات ترابط أثناء التنفيذ وذلك لتنفيذ المهام بشكل أسرع.

هنا مثال بسيط متعدد مؤشرات الترابط في python الذي يطبع الأرقام من 1 إلى 10 ، عن طريق وضع مؤشر ترابط منفصل لكل بيان الطباعة.

 `import threading 
 
 def print_number(number): 
    print(number) 
 
 if __name__ == "__main__": 
    for i in range(1, 11): 
        threading.Thread(target=print_number, args=(i,)).start() 
` 

#### معلومات اكثر:

*   [مواضيع (ويكيبيديا)](https://en.wikipedia.org/wiki/Thread_(computing))
*   [فهم متعددة](http://www.nakov.com/inetjava/lectures/part-1-sockets/InetJava-1.3-Multithreading.html)