---
title: "Common SQL Queries"
date: 2021-01-04T08:39:08-04:00
draft: false
---


### Deleting a user's account and associated data
```sql
--- Confirm the user's existance and get their User ID
select * from users where username = 'some-fake-user';

--- Delete relational rows & user row
delete from user_preferences where user_id = <user_id>;
delete from email_logs where user_id = <user_id>;
delete from channel_bans where user_id = <user_id>;
delete from apps where user_id = <user_id>;
delete from oauth_access_grants where resource_owner_id = <user_id>;
delete from oauth_access_tokens where resource_owner_id = <user_id>;
delete from oauth_applications where owner_id = <user_id>;
delete from users where id = <user_id>;
```
