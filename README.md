# Sticker STAGING Wordpress Plugin
A powerful tool to create and sync WordPress staging sites with production, featuring safe database cloning and URL replacement.

== Description ==
DISCLAIMER: This plugin is distributed without any warranty. The author is not responsible for any issues that may arise from its use. Use at your own risk.
The **Sticker STAGING Plugin** is a robust tool for WordPress developers and site administrators to manage staging environments with ease. It allows you to create a full copy of your WordPress site to a staging directory, clone the database, perform safe URL replacements (including serialized data), and synchronize changes between production and staging environments. Key features include:

– **Create Staging Site**: Copy your entire WordPress site (files and database) to a staging environment.
– **Pull from Production**: Sync production files and database to staging, overwriting existing staging data.
– **Push to Production**: Safely push changes from staging to production with automatic backups to prevent data loss.
– **Safe URL Replacement**: Handles serialized data correctly to prevent corruption during URL replacements.
– **Database Management**: Clone production database to staging and manage database credentials manually.
– **Security Features**: Adds `.htaccess` protection and `robots.txt` to prevent indexing of the staging site.
– **Logging**: Detailed logs for all operations, stored in `wp-content/staging_logs/`.
– **Backup**: Automatically creates backups before pushing to production, stored in `wp-content/backups/`.

This plugin is ideal for developers who need a reliable staging solution without relying on hosting provider tools. It provides full control over the staging process, ensuring safe and efficient management of WordPress environments.

**Warning**: The push-to-production feature overwrites live site data. Always ensure you have a backup before performing a push operation.

== Installation ==
1. Upload the `sticker-staging` folder to the `/wp-content/plugins/` directory.
2. Activate the plugin through the 'Plugins' menu in WordPress.
3. Navigate to the **Staging** menu in the WordPress admin dashboard.
4. Enter your staging database credentials (database name, user, password, and host) in the settings section and save them.
5. Use the provided buttons to create a staging site, pull from production, push to production, or delete the staging site.

== Frequently Asked Questions ==
= Do I need a separate database for the staging site? =
Yes, you need to provide a separate database for the staging environment. Enter the database credentials in the plugin settings before creating or pulling to the staging site.

= Will the push-to-production feature overwrite my live site? =
Yes, the push-to-production feature will overwrite your production database and selected files (themes and plugins). The plugin creates a backup of the production database before pushing, stored in `wp-content/backups/`. Always verify your backup before pushing.

= How does the plugin handle serialized data during URL replacement? =
The plugin uses a safe URL replacement method that correctly handles serialized data in the database, preventing corruption of complex data structures used by plugins like Elementor or WooCommerce.

= Can I exclude certain files or directories from copying? =
Yes, the plugin excludes the staging directory, backups, and logs from being copied during the create or pull operations. Additional exclusions can be customized by modifying the plugin code if needed.

= What happens to the staging database when I delete the staging site? =
The plugin deletes only the staging directory and files. The staging database is not deleted to prevent accidental data loss, as it is manually configured.

= Is the staging site protected from public access? =
Yes, the plugin adds an `.htaccess` file to the staging directory to restrict access and a `robots.txt` file to prevent search engine indexing.

== Screenshots ==
1. Admin interface showing staging settings and action buttons.
2. Example of the staging site creation process with status logs.
3. Confirmation dialog for push-to-production with backup checkbox and text confirmation.

== Changelog ==

= 1.2 =
* Improved URL replacement to handle serialized data more robustly.
* Added automatic `.htaccess` creation for staging site with correct rewrite rules.
* Enhanced logging for better debugging and transparency.
* Added backup creation before pushing to production.

= 1.1 =
* Added support for manual database credential input.
* Improved file copying to exclude sensitive directories like backups and logs.
* Introduced confirmation steps for dangerous operations like push-to-production.

= 1.0 =
* Initial release with core staging functionality: create, pull, push, and delete.

== Upgrade Notice ==

= 1.2 =
This update improves URL replacement for serialized data and adds better logging. Please test on a non-production site first, as the push feature will overwrite live data.

== License ==
This plugin is licensed under the GPLv2 or later. You are free to use, modify, and distribute it under the terms of the GNU General Public License.

== Support ==
For support, please contact the author at info@sticker.rs or visit the plugin support forum on WordPress.org.

== Donate ==
If you find this plugin useful, consider supporting its development with a donation via [PayPal](https://paypal.me/StickerPlugin) or [Patreon](https://patreon.com/WordpressSTAGINGplugin).

# Sticker STAGING Wordpress Plugin

Моћан алат за креирање и синхронизацију WordPress staging сајтова са продукцијом, са безбедним клонирањем базе података и заменом URL-ова.

== Опис ==
ОДРИЦАЊЕ ОД ОДГОВОРНОСТИ: Овај плагин се дистрибуира без икакве гаранције. Аутор не сноси одговорност за евентуалне проблеме који могу настати његовом употребом. Користите на сопствени ризик.

Sticker STAGING Plugin је поуздан алат за WordPress девелопере и администраторе сајтова који желе лако да управљају staging окружењима. Омогућава вам да направите комплетну копију вашег WordPress сајта у staging директоријум, клонрате базу података, извршите безбедне замене URL-ова (укључујући серијализоване податке) и синхронизујете измене између продукције и staging окружења. Кључне функције укључују:

– **Креирање staging сајта:** Копирање целог WordPress сајта (фајлова и базе) у staging окружење.
– **Повлачење са продукције (Pull):** Синхронизација фајлова и базе са продукционог сајта на staging, при чему се бришу постојећи staging подаци.
– **Слање на продукцију (Push):** Безбедно пребацивање измена са staging-а на продукцију уз аутоматско прављење бекапа ради заштите од губитка података.
– **Безбедна замена URL-ова:** Исправна обрада серијализованих података да би се спречило оштећење базе током замене URL-ова.
– **Управљање базом:** Клонирање продукционе базе на staging и ручно управљање креденцијалима базе.
– **Безбедносне функције:** Додавање .htaccess заштите и robots.txt фајла да би се спречило индексирање staging сајта.
– **Логови:** Детаљни логови свих операција, чувају се у wp-content/staging_logs/.
– **Бекап:** Аутоматско креирање бекапа пре слања на продукцију, чувано у wp-content/backups/.

Овај плагин је идеалан за девелопере којима је потребна поуздана staging опција без ослањања на алате хостинг провајдера. Даје вам потпуну контролу над staging процесом и омогућава сигурно и ефикасно управљање WordPress окружењима.

Упозорење: Функција push-to-production преписује податке на live сајту. Увек се постарајте да имате бекап пре него што покренете ову опцију.

== Инсталација ==

Отпремите фолдер sticker-staging у директоријум /wp-content/plugins/.

Активирајте плагин кроз мени Додаци (Plugins) у WordPress-у.

Идите на мени Staging у WordPress администраторској контролној табли.

Унесите креденцијале базе за staging (назив базе, корисника, лозинку и хост) у секцији подешавања и сачувајте их.

Користите понуђена дугмад да креирате staging сајт, повучете продукцију, пошаљете измене на продукцију или обришете staging сајт.

== Најчешћа питања ==
= Да ли ми је потребна посебна база за staging? =
Да, потребно је да обезбедите посебну базу за staging окружење. Унесите креденцијале базе у подешавањима пре него што креирате или повучете staging сајт.

= Да ли опција push-to-production преписује мој live сајт? =
Да, ова опција преписује продукциону базу и одабране фајлове (теме и плагине). Плагин пре тога прави бекап продукционе базе и чува га у wp-content/backups/. Пре него што урадите push, уверите се да је бекап валидан.

= Како плагин обрађује серијализоване податке приликом замене URL-ова? =
Плагин користи безбедну методу замене URL-ова која правилно обрађује серијализоване податке у бази, што спречава оштећења у сложеним структурама података које користе додаци попут Елементор-а или WooCommerce-а.

= Могу ли да искључим одређене фајлове или директоријуме из копирања? =
Да, плагин искључује staging директоријум, бекапе и логове током креирања или повлачења staging сајта. Додатна искључења могу се подесити изменом кода плагина.

= Шта се дешава са staging базом када обришем staging сајт? =
Плагин брише само staging директоријум и фајлове. Staging база се не брише како би се спречио случајни губитак података, јер је ручно конфигурисана.

= Да ли је staging сајт заштићен од јавног приступа? =
Да, плагин додаје .htaccess фајл у staging директоријум ради ограничавања приступа, као и robots.txt фајл да спречи индексирање од стране претраживача.

== Screenshots ==

Администраторски интерфејс са staging подешавањима и командним дугмадима.

Пример процеса креирања staging сајта са логовима статуса.

Дијалог за потврду push-to-production операције са опцијом бекапа и текстуалном потврдом.

== Changelog ==

= 1.2 =

Побољшана замена URL-ова за робусније руковање серијализованим подацима.

Аутоматско креирање .htaccess фајла за staging сајт са исправним rewrite правилима.

Унапређени логови за бољи debugging и транспарентност.

Додато аутоматско прављење бекапа пре слања на продукцију.

= 1.1 =

Додата подршка за ручни унос креденцијала базе.

Побољшано копирање фајлова тако да се искључују осетљиви директоријуми попут бекапа и логова.

Уведени додатни кораци потврде за ризичне операције попут push-to-production.

= 1.0 =

Прва верзија са основном staging функционалношћу: креирање, повлачење, слање и брисање.

== Напомена о надоградњи ==

= 1.2 =
Ова верзија побољшава замену URL-ова за серијализоване податке и додаје боље логове. Пре него што покренете на продукцији, тестирајте на тестном сајту, јер push функција преписује live податке.

== Лиценца ==
Овај плагин је лиценциран под GPLv2 или каснијом верзијом. Слободно га можете користити, мењати и дистрибуирати у складу са условима GNU General Public License.

== Подршка ==
За подршку контактирајте аутора на info@sticker.rs или посетите форум за подршку на WordPress.org.

== Донације ==
Ако вам је овај плагин користан, размислите о подршци његовом развоју донацијом путем [PayPal](https://paypal.me/StickerPlugin) или [Patreon](https://patreon.com/WordpressSTAGINGplugin).
