Find the first element in alphabetical order for an array of strings using a loop.
For example, for this array: $a=['my','name','is','john','doe']; the result should be 'doe'.
Please write your answer in PHP 8

```php
$array = ['my', 'name', 'is', 'john', 'doe'];
$count = count($array);

for ($i = 0; $i < $count; $i++) {
    for ($j = $i + 1; $j < $count; $j++) {
        if ($array[$i] > $array[$j]) {
            [$array[$i], $array[$j]] = [$array[$j], $array[$i]];
        }
    }
}

print("{$array[0]}\n");
```

***

There is a `t` table with 3 fields:
`uid` - user ID
`dt` - date and time of message
`s` - text of the message
Each message gets its own row in the database.
Write an SQL query to retrieve date and text of the last message for all users.

```sql
select dt, s from t
	where (uid, dt) in (
		select uid, max(dt) as dt
			from t
			group by uid
	);
```

***

A business has two types of users: staff and clients.
Staff members can perform actions to help run the business while clients interact with the business by buying products and services.
The two types of users aren't completely different however, they both have logins and profiles.
Describe in words (no source code) what classes you'd create to model users for this business and any relationships between classes (no need for properties or methods).

```txt
First of all it will be a base class, maybe even abstract - User.
For user types - StaffUser and ClientUser. They both will extend User class.
```
