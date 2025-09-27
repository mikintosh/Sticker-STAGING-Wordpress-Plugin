# Sticker-STAGING-Wordpress-Plugin
A powerful tool to create and sync WordPress staging sites with production, featuring safe database cloning and URL replacement.

== Description ==

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
If you find this plugin useful, consider supporting its development with a donation via [PayPal](https://paypal.me/yourpaypalusername) or [Patreon](https://www.patreon.com/yourpatreonusername).
