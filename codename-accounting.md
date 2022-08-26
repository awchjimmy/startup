
- 問：某家店這個月進帳多少，`rds.store_id` 換一下
```sql
select sum(rds.partial_amount)
from deposit dep, rel_deposit_store rds
where dep.deposit_id = rds.deposit_id
and rds.store_id = 12
```

```sql
select *
from deposit dep, rel_deposit_store rds
where dep.deposit_id = rds.deposit_id
and rds.store_id = 12
```
