<!-- 
تعريف HMVC:
HMVC هو اختصار لـ "Hierarchical Model-View-Controller"  
هذا النمط المعماري هو تحسين للنمط التقليدي MVC (Model-View-Controller)،
حيث يتم تقسيم التطبيق إلى وحدات أو وحدات نمطية (Modules)، 
كل منها يحتوي على مجموعة من الملفات الخاصة بالنموذج (Model)، العرض (View)، والمتحكم (Controller). 
هذه الوحدات تكون مستقلة وقابلة لإعادة الاستخدام، مما يسهل عملية تطوير وصيانة التطبيقات الكبيرة.

فوائد استخدام HMVC في Laravel:

قابلية إعادة الاستخدام: بفضل تقسيم التطبيق إلى وحدات مستقلة، يمكن إعادة استخدام أجزاء من الكود في مشاريع أخرى بسهولة.
تسهيل الصيانة: يسهل على المطورين صيانة الكود وتحديد أماكن الخطأ بفضل التقسيم الواضح والوحدات الصغيرة.
تنظيم الكود: يساعد على تنظيم الكود بشكل أفضل وتقسيمه إلى أجزاء صغيرة ومترابطة، مما يجعل التطبيق أكثر تنظيماً ووضوحاً.
تحسين الأداء: يمكن أن يساعد في تحسين أداء التطبيق بفضل الفصل بين الوحدات وتقليل التداخل بينه

laravel modules => backage for HMVC  (php > 7.1 , laravel > 5)
https://nwidart.com/laravel-modules

1 install
composer require nwidart/laravel-modules

2 publish
php artisan vendor:publish --provider="Nwidart\Modules\LaravelModulesServiceProvider"

in config => modules.php

3 in composer.jeson
"autoload": {
    "psr-4": {
        "App\\": "app/",
        "Database\\Factories\\": "database/factories/",
        "Database\\Seeders\\": "database/seeders/"
        "Modules\\": "Modules/" // new line
    }
},

4 composer dump

to create module
1 php artisan module:make <module-name>
2 php artisan module:make Blog User Auth => more than module
3 php artisan module:make Blog -p => without any code in controller or route 

to create table
php artisan module:make-migration create_posts_table Blog

to migrate blog tables
php artisan module:migrate Blog

to stop migrate or make this module disable  
php artisan module:disable Blog X php artisan module:enable Blog

when i create module it used 
php artisan module:use Blog
php artisan module:unuse


to make table in database migration 
php artisan module:publish-migration Blog

all comands and how to use 
https://nwidart.com/laravel-modules


 -->