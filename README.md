# pack-redis

## Description

Shinken configuration pack for redis servers. This pack use Temelio plugins to
do some checks.

Today:
* this pack contains only some checks on numeric values from INFO data
* all databases share the same thresholds

## TODO

Need to add more checks to cover more points.

## Objects

### Templates

#### Host templates

* redis: Manage all default thresholds and values for services

#### Service templates

* redis-service: Manage service aggregration

### Services

| Service name                                 | Warning variable                        | Critical variable                      | Duplicate_foreach variable |
|----------------------------------------------|-----------------------------------------|----------------------------------------|----------------------------|
| $KEY$ - Blocked clients                      | _REDIS_BLOCKED_CLIENTS_WARN             | _REDIS_BLOCKED_CLIENTS_CRIT             | _redis_databases          |
| $KEY$ - Connected clients                    | _REDIS_CONNECTED_CLIENTS_WARN           | _REDIS_CONNECTED_CLIENTS_CRIT           | _redis_databases          |
| $KEY$ - Connected slaves                     | _REDIS_CONNECTED_SLAVES_WARN            | _REDIS_CONNECTED_SLAVES_CRIT            | _redis_databases          |
| $KEY$ - Evicted keys                         | _REDIS_EVICTED_KEYS_WARN                | _REDIS_EVICTED_KEYS_CRIT                | _redis_databases          |
| $KEY$ - Expired keys                         | _REDIS_EXPIRED_KEYS_WARN                | _REDIS_EXPIRED_KEYS_CRIT                | _redis_databases          |
| $KEY$ - Hit rate                             | _REDIS_HIT_RATE_WARN                    | _REDIS_HIT_RATE_CRIT                    | _redis_databases          |
| $KEY$ - Instantaneous operations per seconds | _REDIS_INSTANTANEOUS_OPS_PER_SEC_WARN   | _REDIS_INSTANTANEOUS_OPS_PER_SEC_CRIT   | _redis_databases          |
| $KEY$ - Memory fragmentation ratio           | _REDIS_MEM_FRAGMENTATION_RATIO_WARN     | _REDIS_MEM_FRAGMENTATION_RATIO_CRIT     | _redis_databases          |
| $KEY$ - Changes since last backup            | _REDIS_RDB_CHANGES_SINCE_LAST_SAVE_WARN | _REDIS_RDB_CHANGES_SINCE_LAST_SAVE_CRIT | _redis_databases          |
| $KEY$ - Rejected connections                 | _REDIS_REJECTED_CONNECTIONS_WARN        | _REDIS_REJECTED_CONNECTIONS_CRIT        | _redis_databases          |
| $KEY$ - Uptime                               | _REDIS_UPTIME_IN_SECONDS_WARN           | _REDIS_UPTIME_IN_SECONDS_CRIT           | _redis_databases          |

## Default values

    _REDIS_PASSWORD                             ''
    _REDIS_PORT                                 6379
    _REDIS_TIMEOUT                              30

    _REDIS_BLOCKED_CLIENTS_WARN                 1
    _REDIS_BLOCKED_CLIENTS_CRIT                 5
    _REDIS_CONNECTED_CLIENTS_WARN               50
    _REDIS_CONNECTED_CLIENTS_CRIT               100
    _REDIS_CONNECTED_SLAVES_WARN                0
    _REDIS_CONNECTED_SLAVES_CRIT                0
    _REDIS_EVICTED_KEYS_WARN                    50
    _REDIS_EVICTED_KEYS_CRIT                    100
    _REDIS_EXPIRED_KEYS_WARN                    50
    _REDIS_EXPIRED_KEYS_CRIT                    100
    _REDIS_INSTANTANEOUS_OPS_PER_SEC_WARN       500
    _REDIS_INSTANTANEOUS_OPS_PER_SEC_CRIT       1000
    _REDIS_HIT_RATE_WARN                        0.9:
    _REDIS_HIT_RATE_CRIT                        0.8:
    _REDIS_MEM_FRAGMENTATION_RATIO_WARN         3
    _REDIS_MEM_FRAGMENTATION_RATIO_CRIT         4
    _REDIS_RDB_CHANGES_SINCE_LAST_SAVE_WARN     500
    _REDIS_RDB_CHANGES_SINCE_LAST_SAVE_CRIT     1000
    _REDIS_REJECTED_CONNECTIONS_WARN            1
    _REDIS_REJECTED_CONNECTIONS_CRIT            5
    _REDIS_UPTIME_IN_SECONDS_WARN               600:
    _REDIS_UPTIME_IN_SECONDS_CRIT               300:

    _redis_databases                            Database 0 $(0)$
