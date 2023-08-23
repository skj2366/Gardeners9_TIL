# MySQL EXPLAIN (MySql 실행계획)

##
## EXPLAIN
MySQL 서버가 어떠한 쿼리에 대한 실행 계획이 무엇인지 알고 싶을 때 사용하는 명령어

### .e.g
id|select_type|table     |partitions|type  |possible_keys                                       |key                      |key_len|ref                          |rows  |filtered|Extra      |
--+-----------+----------+----------+------+----------------------------------------------------+-------------------------+-------+-----------------------------+------+--------+-----------+
1|PRIMARY    |contents  |          |ALL   |PRIMARY                                             |                         |       |                             |297904|   100.0|           |
1|PRIMARY    |metadata  |          |ref   |metadata_content_id_index                           |metadata_content_id_index|4      |samdb.contents.id            |     1|   100.0|           |
1|PRIMARY    |b2        |          |eq_ref|PRIMARY                                             |PRIMARY                  |82     |samdb.metadata.author        |     1|   100.0|           |
1|PRIMARY    |b3        |          |eq_ref|PRIMARY                                             |PRIMARY                  |82     |samdb.metadata.modr_id       |     1|   100.0|           |
1|PRIMARY    |b4        |          |eq_ref|PRIMARY                                             |PRIMARY                  |5      |func                         |     1|   100.0|Using where|
1|PRIMARY    |b5        |          |eq_ref|PRIMARY                                             |PRIMARY                  |8      |samdb.contents.cms_content_id|     1|   100.0|           |
1|PRIMARY    |c         |          |eq_ref|PRIMARY                                             |PRIMARY                  |8      |func,func                    |     1|   100.0|Using where|
1|PRIMARY    |a         |          |eq_ref|PRIMARY                                             |PRIMARY                  |82     |samdb.contents.user_id       |     1|   100.0|Using index|
1|PRIMARY    |<derived5>|          |ref   |<auto_key0>                                         |<auto_key0>              |82     |samdb.a.user_id              |    10|   100.0|Using where|
5|DERIVED    |role_user |          |index |PRIMARY,role_user_role_id_foreign,role_user_users_fk|role_user_users_fk       |82     |                             | 18178|   100.0|Using index|

> 이건 왜 마크다운에서 자동으로 테이블화 안되는거지 ..

## MySQL 옵티마이저 구조
- ... 옵티마이저
- 비용 기반 옵티마이저
  - mysql을 포함하여 최근에는 비용 기반 옵티마이저

## ICP: Index Condition Pushdown
- `show variables like 'optimizer_switch';`
  - `...index_condition_pushdown=on;...` 해당 속성 on, off로 옵션 확인 가능
  - 기본적으로 on 

## Why?
- 일감때문에 ...
- 화자의 마음을 이해하기 힘들다.





