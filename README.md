# delete_cache_sql_drupal8
delete_cache_sql_drupal8

rm -rf sites/default/files/php/twig/* && echo "SHOW TABLES LIKE 'cache%'" | $(drush sql-connect) | tail -n +2 | xargs -L1 -I% echo "TRUNCATE TABLE %;" | $(drush sql-connect) -v
