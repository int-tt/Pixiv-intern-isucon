Pixiv-intern2014w
=================

ぴくしぶインターンGithub選考用

最初のスコア
---------

    [isucon@ip-172-31-19-252 ~]$ ./benchmarker bench
    18:28:00 type:info	message:launch benchmarker
    18:28:00 type:warning	message:Result not sent to server because API key is not set
    18:28:00 type:info	message:init environment
    18:28:07 type:info	message:run benchmark workload: 1
    18:29:07 type:info	message:finish benchmark workload: 1
    18:29:12 type:info	message:check banned ips and locked users report
    18:29:31 type:report	count:banned ips	value:8
    18:29:31 type:report	count:locked users	value:2568
    18:29:31 type:info	message:Result not sent to server because API key is not set
    18:29:31 type:score	success:7600	fail:0	score:1642
    [isucon@ip-172-31-19-252 ~]$

##インスタンス再起動したので...
        [isucon@ip-172-31-15-229 ~]$ ./benchmarker bench
        20:09:01 type:info      message:launch benchmarker
        20:09:01 type:warning   message:Result not sent to server because API key is not set
        20:09:01 type:info      message:init environment
        20:09:08 type:info      message:run benchmark workload: 1
        20:10:09 type:info      message:finish benchmark workload: 1
        20:10:14 type:info      message:check banned ips and locked users report
        20:10:33 type:report    count:banned ips        value:6
        20:10:33 type:report    count:locked users      value:2568
        20:10:33 type:info      message:Result not sent to server because API key is not set
        20:10:33 type:score     success:7760    fail:0  score:1677

