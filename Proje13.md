city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.
customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.
customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.

-- 1) city 🇨🇮 LEFT JOIN country: şehir ve ülke isimleri
SELECT
  ci.city,
  co.country
FROM city AS ci
LEFT JOIN country AS co
  ON ci.country_id = co.country_id
ORDER BY co.country, ci.city;

-- 2) customer RIGHT JOIN payment: payment_id + müşteri ad/soyad
SELECT
  p.payment_id,
  c.first_name,
  c.last_name
FROM customer AS c
RIGHT JOIN payment AS p
  ON p.customer_id = c.customer_id
ORDER BY p.payment_id;

-- 3) customer FULL JOIN rental: rental_id + müşteri ad/soyad
SELECT
  r.rental_id,
  c.first_name,
  c.last_name
FROM customer AS c
FULL JOIN rental AS r
  ON r.customer_id = c.customer_id
ORDER BY r.rental_id;
