select hire_date, first_name, last_name from 
employees where hire_date < date('2011-02-15 00:00:00');
select * from tracks where composer is null; # composer = null will return error
select * from invoices where billing_country = 'Germany' 
order by total desc limit 10;
select count(id) from invoices where 
billing_city = 'Santiago';

select country, count(id) from customers group by 
country;
select unit_price, count(id) from tracks group by 
unit_price;

select country, count(id) from customers 
group by country
order by count desc
limit 3;

select name ,title from artists join albums on artists.id=albums.artist_id;
select name, title from albums join tracks on albums.id = tracks.album_id

select name, title from albums join artists on artists.id = albums.artist_id
order by name asc;
select first_name, last_name, total from customers join invoices on customers.id=invoices.customer_id order by total desc;
select * from customers join invoices on customers.id=invoices.customer_id
order by total desc
limit 1

select * from albums join artists 
on artists.id = albums.artist_id 
where name = 'Aerosmith';

select * from albums join tracks on albums.id = tracks.album_id 
where name = 'Midnight';

select artists.name from artists join albums on artists.id = albums.artist_id 
join tracks on albums.id = tracks.album_id where tracks.name = 'Midnight';
select count(albums.id) from albums join artists on albums.artist_id=artists.id where artists.name= 'Iron Maiden';

select artists.name, count(artists.id) from artists join albums on artists.id=albums.artist_id
group by artists.name
order by artists.name asc;

select albums.title, count(albums.id) from albums
join tracks on albums.id = tracks.album_id
group by albums.title
order by albums.title asc;

select artists.id, artists.name, count(albums.id) from artists 
join albums on albums.artist_id=artists.id
group by artists.id
order by count(albums.id) desc
limit 1;

select albums.id, albums.title, albums.artist_id, count(tracks.id) from albums 
join tracks on albums.id=tracks.album_id
group by albums.id
order by count(tracks.id) desc
limit 1;

select customers.first_name, customers.last_name, 
sum(invoices.total) from customers join 
invoices on customers.id=invoices.customer_id
group by customers.id
order by sum(invoices.total) desc
limit 5;

select albums.id, albums.title, albums.artist_id,
count(tracks.id) from albums
join tracks on albums.id=tracks.album_id
group by albums.id
order by count(tracks.id) desc;

