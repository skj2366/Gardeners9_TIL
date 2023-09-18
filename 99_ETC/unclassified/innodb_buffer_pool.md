# innodb buffer pool

``` sql
SELECT @@innodb_buffer_pool_size/1024/1024 AS 'innodb_buffer_pool_size(MB)';
SELECT @@innodb_log_file_size/1024/1024 AS 'innodb_log_file_size(MB)';

SELECT @@innodb_buffer_pool_dump_pct;
SELECT @@innodb_buffer_pool_load_at_startup;
SELECT @@innodb_buffer_pool_dump_at_shutdown;
SELECT @@innodb_buffer_pool_filename;

SHOW status LIKE '%innodb_buffer_pool%';
```
## SHOW status LIKE '%innodb_buffer_pool%'

- Innodb_buffer_pool_dump_status
  - 버퍼풀에 보관된 페이지를 기록한 상태
- Innodb_buffer_pool_load_status
  - 버퍼풀이 이전 시점에 해당하는 페이지를 읽음으로 워밍업을 진행한 페이지 수
- Innodb_buffer_pool_resize_status
  - 버퍼풀의 크기를 동적으로 조정하는 작업 상태
- Innodb_buffer_pool_pages_data
  - 전체 버퍼풀에서 현재 사용중인 버퍼풀 페이지 수
- Innodb_buffer_pool_bytes_data
  - 전체 버퍼풀에서 현재 사용중인 버퍼풀 바이트 수
- Innodb_buffer_pool_pages_dirty
  - 버퍼풀의 데이터 중 변경된 페이지 수 (더티페이지 수)
- Innodb_buffer_pool_bytes_dirty
  - 버퍼풀의 데이터 중 변경된 바이트 수(더티 데이터 수)
- Innodb_buffer_pool_pages_flushed
  - 버퍼풀에서 플러시한 페이지 수
- Innodb_buffer_pool_pages_free
  - 전체 버퍼풀에서 사용하지 않은(사용가능한) 페이지 수
- Innodb_buffer_pool_pages_misc
  - Row lock, hash index 와 같이 오버헤드에 할당되어 사용된 버퍼풀의 페이지 수
- Innodb_buffer_pool_pages_total
  - 전체 버퍼풀의 페이지 수
- Innodb_buffer_pool_read_ahead_rnd
  - 랜덤으로 미리 읽기가 발생한 페이지 수
- Innodb_buffer_pool_read_ahread
  - 미리 읽기 백그라운드 스레드가 버퍼풀로 미리 읽어들인 페이지 수
- Innodb_buffer_pool_read_ahead_evicted
  - 버퍼풀에 미리 읽어들인 페이지 중 사용되지 않고 제거된 페이지 수
- Innodb_buffer_pool_read_requests
  - 버퍼풀에서 논리적인 읽기 요청 횟수
- Innodb_buffer_pool_reads
  - 버퍼풀에 데이터가 없어서 디스크에서 직접 읽은 논리적 수
- Innodb_buffer_pool_wait_free
  - 페이지를 읽거나 생성할때 사용가능한 클린 페이지가 없을 경우 InnoDB가 더티페이지를 비우고 그 작업이 끝나기를 기다리는 값
- Innodb_buffer_pool_write_requests
  - 버퍼풀에 대한 쓰기 횟수


***


## DATE 
> 2023-09-18 13:54