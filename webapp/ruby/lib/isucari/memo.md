

SELECT * FROM `items` WHERE (`seller_id` = 1 OR `buyer_id` = 1) AND `status` IN ("on_sale", "trading", "sold_out", "stop", "cancel") LIMIT 1;


AND (`created_at` <  2020-08-04 11:51:30 OR (`created_at` <= 2020-08-04 11:51:30 AND `id` < 10000)) 
 ORDER BY `created_at` DESC, `id` DESC LIMIT #11;





SELECT i.*,  
        s.id sid,s.account_name san,s.num_sell_items ssi,
        b.id bid,b.account_name ban,b.num_sell_items bsi,
        t.id tid,t.status ts
 FROM `items` i LEFT JOIN `users` s ON i.seller_id = s.id 
              LEFT JOIN `users` b ON i.buyer_id = b.id
              LEFT JOIN `transaction_evidences` t ON i.id = t.item_id
 WHERE (i.`seller_id` = 1 OR i.`buyer_id` = 1) AND i.`status` IN ("on_sale", "trading", "sold_out", "stop", "cancel") LIMIT 1;


              LEFT JOIN `categories` c ON i.category_id = c.id
,