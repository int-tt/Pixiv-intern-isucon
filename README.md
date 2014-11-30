Pixiv-intern2014w
=================

ぴくしぶインターンGithub選考課題

##初期スコア
    #./benchmarker bench --workload N --init /home/isucon/init.sh
    success:7310	fail:0	score:1579 worload = 1
    success:16020	fail:0	score:3462 workload = 4
##phpの変更点
locked_users内でforeach毎に同じSQLが宣言されていたのでforeach外で宣言するように変更

    success:7360	fail:0	score:1590 workload = 1
    success:16060	fail:0	score:3471 workload = 4

同じようにbanned_ipsでも同一の処理を行いました

    success:7860	fail:0	score:1658　workload = 1
    success:15430	fail:0	score:3334 worload = 4

ここまでやった後

>/report は1分以内にレスポンスを返さなければならない

という文より集計の高速化はそれほど重要では無いと判断し、ベンチ指標の

>HTTP GET/POST リクエストの成功数をベースにする。

から表示のページ表示の高速化に焦点を変更しました。

使われているライブラリのlimonadeはページレンダリングにしか使われておらず、大きなwebサイトでも無かったので
limonadeを削除しました。

    success:7800	fail:0	score:1685 workload = 1
    success:15920	fail:0	score:3440 workload = 4

##MYSQL周り
x3largeと非常に大きいインスタンスでやっているのでdbが沢山メモリを使えるように変更

    key_buffer_size = 32M
    sort_buffer_size = 2M
    read_buffer_size = 2M
    query_cache_type = 1

    max_connections=450
    thread_cache=450

    innodb_buffer_pool_size = 1024M


##エフェメラルポートのレンジ拡張
デフォルトだとTCP通信に使えるポート数が多くないのでsysctl.confに設定を追記

    net.ipv4.tcp_tw_recycle = 1
    net.ipv4.tcp_tw_reuse = 1
    net.ipv4.tcp_fin_timeout = 30
    net.ipv4.ip_local_port_range = 20000 61000

#最終スコア
    success:37410	fail:0	score:8081
    success:71180	fail:0	score:15377
