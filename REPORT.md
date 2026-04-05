## lab01

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [ ] 1. Ознакомиться со ссылками учебного материала
- [ ] 2. Выполнить инструкцию учебного материала
- [ ] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```bash
$ export GITHUB_USERNAME=<имя_пользователя>
$ export GIST_TOKEN=<сохраненный_токен>
$ alias edit=<nano|vi|vim|subl>
```

```sh
$ mkdir -p ${yuliyavroma-spec}/workspace
$ cd ${yuliyavroma-spec}/workspace
$ pwd
$ cd ..
$ pwd
```

```sh
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```

```sh
# Debian
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
$ tar -xf node-v6.11.5-linux-x64.tar.xz
$ rm -rf node-v6.11.5-linux-x64.tar.xz
$ mv node-v6.11.5-linux-x64 node
```

```sh
$ ls node/bin
$ echo ${PATH}
$ export PATH=${PATH}:`pwd`/node/bin
$ echo ${PATH}
$ mkdir scripts
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate
```

```sh
$ gem install gist
```

```sh
$ (umask 0077 && echo ${GIST_TOKEN} > ~/.gist)
```

## Report

```sh
$ export LAB_NUMBER=01
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```

## Links

### Unix commands

- [ar](https://en.wikipedia.org/wiki/Ar_(Unix))
- [cat](https://en.wikipedia.org/wiki/Cat_(Unix))
- [cd](https://en.wikipedia.org/wiki/Cd_(command))
- [cp](https://en.wikipedia.org/wiki/Cp_(Unix))
- [cut](https://en.wikipedia.org/wiki/Cut_(Unix))
- [echo](https://en.wikipedia.org/wiki/Echo_(command))
- [env](https://en.wikipedia.org/wiki/Env_(shell))
- [ex](https://en.wikipedia.org/wiki/Ex_(editor))
- [file](https://en.wikipedia.org/wiki/File_(command))
- [find](https://en.wikipedia.org/wiki/Find)
- [ls](https://en.wikipedia.org/wiki/Ls)
- [man](https://en.wikipedia.org/wiki/Man_page)
- [mkdir](https://en.wikipedia.org/wiki/Mkdir)
- [mv](https://en.wikipedia.org/wiki/Mv)
- [nm](https://en.wikipedia.org/wiki/Nm_(Unix))
- [ps](https://en.wikipedia.org/wiki/Ps_(Unix))
- [pwd](https://en.wikipedia.org/wiki/Pwd)
- [rm](https://en.wikipedia.org/wiki/Rm_(Unix))
- [sed](https://en.wikipedia.org/wiki/Sed)
- [touch](https://en.wikipedia.org/wiki/Touch_(Unix))

### Package Managers

- [apt](http://help.ubuntu.ru/wiki/apt) | [dnf](https://en.wikipedia.org/wiki/DNF_(software)) | [yum](https://fedoraproject.org/wiki/Yum/ru)
- [brew](https://brew.sh) | [linuxbrew](http://linuxbrew.sh)
- [npm](https://docs.npmjs.com)

### Software

- [curl](https://www.gitbook.com/book/bagder/everything-curl/details)
- [wget](https://www.gnu.org/software/wget/manual/wget.pdf)
- [clang](https://clang.llvm.org)
- [g++](https://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/G_002b_002b-and-GCC.html)
- [make](https://en.wikipedia.org/wiki/Make_(software))
- [open](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/open.1.html)
- [openssl](https://www.openssl.org)
- [nano](https://www.nano-editor.org)
- [tree](https://linux.die.net/man/1/tree)
- [vim](http://www.vim.org)

## Homework

1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
11. Найдите *топ10* самых "тяжёлых".

```
Copyright (c) 2015-2021 The ISC Authors
```
## Домашнее задание

### 1. Скачивание библиотеки

`$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`

### 2. Разархивирование

`tar -xzf boost_1_69_0.tar.gz -C ~/`

Распаковано в ~/boost_1_69_0

### 3. Количество файлов (без вложенных)

`find ~/boost_1_69_0 -maxdepth 1 -type f | wc -l`

 **Результат:** 16

### 4. Количество файлов (с вложенными)

`find ~/boost_1_69_0 -type f | wc -l`

**Результат:** 61838

### 5. Подсчёт заголовочных файлов

`find ~/boost_1_69_0 -type f \( -name "*.hpp" -o -name "*.h" \) | wc -l`

**Результат:** 15208

### 6. Путь до any.hpp

`find ~/boost_1_69_0 -name "any.hpp"`

**Результат:**
- /home/yulia/boost_1_69_0/boost/fusion/include/any.hpp
- /home/yulia/boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
- /home/yulia/boost_1_69_0/boost/fusion/algorithm/query/any.hpp
- /home/yulia/boost_1_69_0/boost/xpressive/detail/utility/any.hpp
- /home/yulia/boost_1_69_0/boost/type_erasure/any.hpp
- /home/yulia/boost_1_69_0/boost/any.hpp
- /home/yulia/boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
- /home/yulia/boost_1_69_0/boost/hana/fwd/any.hpp
- /home/yulia/boost_1_69_0/boost/hana/any.hpp
- /home/yulia/boost_1_69_0/boost/proto/detail/any.hpp


### 7. Файлы с boost::asio

`grep -r "boost::asio" ~/boost_1_69_0 --files-with-matches`

**Результат:**
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/send_to/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/receive_buffer_size.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/out_of_band_inline.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/send_buffer_size.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/debug.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/reuse_address.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/remote_endpoint/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/remote_endpoint/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/receive/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/connect/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/connect/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_receive_from/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_receive_from/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/release/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/release/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/get_io_context.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/send/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/open/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/open/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/local_endpoint/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/local_endpoint/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/receive_from/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/bytes_readable.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/io_control/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/io_control/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/get_io_service.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/enable_connection_aborted.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/set_option/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/set_option/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/receive_low_watermark.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_wait.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_receive/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_receive/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload3.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload4.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/wait/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/wait/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/keep_alive.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/linger.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/shutdown/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/shutdown/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ip__address/address.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ip__address/operator_eq_/overload3.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ip__address/operator_eq_/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ip__address/to_v4.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ip__address/to_v6.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ip__address/address/overload3.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ip__address/address/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ip__address/operator_eq_.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/buffer_copy.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/transfer_at_least.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/null_buffers/value_type.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/placeholders__results.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/buffer_cast.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/error__netdb_category.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/system_timer.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/read/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/read/overload9.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/read/overload3.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/read/overload6.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/read/overload10.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/read/overload5.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/read/overload2.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ConnectHandler.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/io_context__work/work.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/io_context__work/get_io_context.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/io_context__work/get_io_service.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/io_context__work/work/overload1.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ReadHandler.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/transfer_exactly.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__ssl__error__stream_errors__gt_.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/reference/ssl__rfc2818_verification.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/index.html
/home/yulia/boost_1_69_0/doc/html/boost_asio/net_ts.html
/home/yulia/boost_1_69_0/doc/html/process/reference.html
/home/yulia/boost_1_69_0/doc/html/boost/process/std_out.html
/home/yulia/boost_1_69_0/doc/html/boost/process/async_pipe.html
/home/yulia/boost_1_69_0/doc/html/boost/process/spawn.html
/home/yulia/boost_1_69_0/doc/html/boost/process/std_in.html
/home/yulia/boost_1_69_0/doc/html/boost/process/on_exit.html
/home/yulia/boost_1_69_0/libs/fiber/doc/callbacks.qbk
/home/yulia/boost_1_69_0/libs/fiber/doc/asio.qbk
/home/yulia/boost_1_69_0/libs/fiber/doc/fibers.qbk
/home/yulia/boost_1_69_0/libs/fiber/doc/integration.qbk
/home/yulia/boost_1_69_0/libs/fiber/examples/asio/autoecho.cpp
/home/yulia/boost_1_69_0/libs/fiber/examples/asio/ps/publisher.cpp
/home/yulia/boost_1_69_0/libs/fiber/examples/asio/ps/subscriber.cpp
/home/yulia/boost_1_69_0/libs/fiber/examples/asio/ps/server.cpp
/home/yulia/boost_1_69_0/libs/fiber/examples/asio/exchange.cpp
/home/yulia/boost_1_69_0/libs/fiber/examples/asio/round_robin.hpp
/home/yulia/boost_1_69_0/libs/thread/test/test_9303.cpp
/home/yulia/boost_1_69_0/libs/log/doc/tmp/sinks_reference.xml
/home/yulia/boost_1_69_0/libs/log/src/syslog_backend.cpp
/home/yulia/boost_1_69_0/libs/coroutine2/doc/motivation.qbk
/home/yulia/boost_1_69_0/libs/coroutine2/doc/coro.qbk
/home/yulia/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__http__error.html
/home/yulia/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__basic_timeout_socket/async_write_some.html
/home/yulia/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__basic_timeout_socket/async_read_some.html
/home/yulia/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload1.html
/home/yulia/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload3.html
/home/yulia/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload2.html
/home/yulia/boost_1_69_0/libs/beast/doc/html/beast/more_examples/expect_100_continue_server.html
/home/yulia/boost_1_69_0/libs/beast/doc/html/beast/using_io/writing_composed_operations.html
/home/yulia/boost_1_69_0/libs/beast/doc/html/beast/using_io/example_detect_ssl.html
/home/yulia/boost_1_69_0/libs/beast/doc/qbk/03_core/1_asio.qbk
/home/yulia/boost_1_69_0/libs/beast/doc/qbk/07_concepts/Streams.qbk
/home/yulia/boost_1_69_0/libs/beast/doc/qbk/07_concepts/DynamicBuffer.qbk
/home/yulia/boost_1_69_0/libs/beast/doc/qbk/08_design/3_websocket_zaphoyd.qbk
/home/yulia/boost_1_69_0/libs/beast/doc/qbk/08_design/4_faq.qbk
/home/yulia/boost_1_69_0/libs/beast/doc/qbk/reference.qbk
/home/yulia/boost_1_69_0/libs/beast/doc/qbk/00_main.qbk
/home/yulia/boost_1_69_0/libs/beast/doc/docca/include/docca/doxygen.xsl
/home/yulia/boost_1_69_0/libs/beast/example/doc/http_examples.hpp
/home/yulia/boost_1_69_0/libs/beast/example/common/session_alloc.hpp
/home/yulia/boost_1_69_0/libs/beast/example/common/detect_ssl.hpp
/home/yulia/boost_1_69_0/libs/beast/example/common/root_certificates.hpp
/home/yulia/boost_1_69_0/libs/beast/example/common/server_certificate.hpp
/home/yulia/boost_1_69_0/libs/beast/example/cppcon2018/net.hpp
/home/yulia/boost_1_69_0/libs/beast/example/http/client/coro/http_client_coro.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/client/sync/http_client_sync.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/client/sync-ssl/http_client_sync_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/client/async-ssl/http_client_async_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/client/coro-ssl/http_client_coro_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/client/crawl/http_crawl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/client/async/http_client_async.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/stackless/http_server_stackless.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/coro/http_server_coro.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/flex/http_server_flex.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/sync/http_server_sync.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/small/http_server_small.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/fast/http_server_fast.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/sync-ssl/http_server_sync_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/async-ssl/http_server_async_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/coro-ssl/http_server_coro_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/stackless-ssl/http_server_stackless_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/http/server/async/http_server_async.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/client/coro/websocket_client_coro.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/client/sync/websocket_client_sync.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/client/sync-ssl/websocket_client_sync_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/client/async-ssl/websocket_client_async_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/client/coro-ssl/websocket_client_coro_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/client/async/websocket_client_async.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/server/stackless/websocket_server_stackless.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/server/coro/websocket_server_coro.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/server/sync/websocket_server_sync.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/server/fast/websocket_server_fast.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/server/sync-ssl/websocket_server_sync_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/server/async-ssl/websocket_server_async_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/server/coro-ssl/websocket_server_coro_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/server/stackless-ssl/websocket_server_stackless_ssl.cpp
/home/yulia/boost_1_69_0/libs/beast/example/websocket/server/async/websocket_server_async.cpp
/home/yulia/boost_1_69_0/libs/beast/example/advanced/server-flex/advanced_server_flex.cpp
/home/yulia/boost_1_69_0/libs/beast/example/advanced/server/advanced_server.cpp
/home/yulia/boost_1_69_0/libs/beast/example/echo-op/echo_op.cpp
/home/yulia/boost_1_69_0/libs/beast/test/doc/exemplars.cpp
/home/yulia/boost_1_69_0/libs/beast/test/doc/http_snippets.cpp
/home/yulia/boost_1_69_0/libs/beast/test/doc/core_snippets.cpp
/home/yulia/boost_1_69_0/libs/beast/test/doc/websocket_snippets.cpp
/home/yulia/boost_1_69_0/libs/beast/test/doc/core_examples.cpp
/home/yulia/boost_1_69_0/libs/beast/test/doc/http_examples.cpp
/home/yulia/boost_1_69_0/libs/beast/test/extras/include/boost/beast/test/yield_to.hpp
/home/yulia/boost_1_69_0/libs/beast/test/extras/include/boost/beast/test/sig_wait.hpp
/home/yulia/boost_1_69_0/libs/beast/test/extras/include/boost/beast/test/websocket.hpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/span_body.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/file_body.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/chunk_encode.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/dynamic_body.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/write.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/serializer.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/basic_parser.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/message_fuzz.hpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/parser.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/read.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/http/test_parser.hpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/read_size.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/flat_buffer.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/buffers_suffix.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/buffers_cat.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/buffered_read_stream.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/flat_static_buffer.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/bind_handler.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/buffer_test.hpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/type_traits.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/buffers_prefix.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/buffer.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/multi_buffer.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/buffers_adapter.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/core/static_buffer.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/utf8_checker.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/read2.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/handshake.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/accept.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/write.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/ping.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/stream.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/doc_snippets.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/close.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/test.hpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/websocket/read1.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/experimental/icy_stream.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/experimental/flat_stream.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/experimental/timeout_socket.cpp
/home/yulia/boost_1_69_0/libs/beast/test/beast/experimental/timeout_service.cpp
/home/yulia/boost_1_69_0/libs/beast/test/bench/buffers/bench_buffers.cpp
/home/yulia/boost_1_69_0/libs/beast/test/bench/parser/bench_parser.cpp
/home/yulia/boost_1_69_0/libs/beast/test/bench/parser/nodejs_parser.hpp
/home/yulia/boost_1_69_0/libs/beast/test/bench/wsload/wsload.cpp
/home/yulia/boost_1_69_0/libs/beast/CHANGELOG.md
/home/yulia/boost_1_69_0/libs/coroutine/doc/html/coroutine/motivation.html
/home/yulia/boost_1_69_0/libs/coroutine/doc/motivation.qbk
/home/yulia/boost_1_69_0/libs/coroutine/doc/coro.qbk
/home/yulia/boost_1_69_0/libs/process/doc/tutorial.qbk
/home/yulia/boost_1_69_0/libs/process/doc/autodoc.xml
/home/yulia/boost_1_69_0/libs/process/doc/extend.qbk
/home/yulia/boost_1_69_0/libs/process/example/wait.cpp
/home/yulia/boost_1_69_0/libs/process/example/async_io.cpp
/home/yulia/boost_1_69_0/libs/process/example/io.cpp
/home/yulia/boost_1_69_0/libs/process/test/async_system_future.cpp
/home/yulia/boost_1_69_0/libs/process/test/on_exit.cpp
/home/yulia/boost_1_69_0/libs/process/test/async_system_stackful.cpp
/home/yulia/boost_1_69_0/libs/process/test/system_test2.cpp
/home/yulia/boost_1_69_0/libs/process/test/system_test1.cpp
/home/yulia/boost_1_69_0/libs/process/test/spawn_fail.cpp
/home/yulia/boost_1_69_0/libs/process/test/async_fut.cpp
/home/yulia/boost_1_69_0/libs/process/test/wait.cpp
/home/yulia/boost_1_69_0/libs/process/test/bind_stderr.cpp
/home/yulia/boost_1_69_0/libs/process/test/async_system_stackful_except.cpp
/home/yulia/boost_1_69_0/libs/process/test/bind_stdout.cpp
/home/yulia/boost_1_69_0/libs/process/test/async.cpp
/home/yulia/boost_1_69_0/libs/process/test/on_exit2.cpp
/home/yulia/boost_1_69_0/libs/process/test/bind_stdout_stderr.cpp
/home/yulia/boost_1_69_0/libs/process/test/on_exit3.cpp
/home/yulia/boost_1_69_0/libs/process/test/bind_stdin.cpp
/home/yulia/boost_1_69_0/libs/process/test/spawn.cpp
/home/yulia/boost_1_69_0/libs/process/test/exit_code.cpp
/home/yulia/boost_1_69_0/libs/process/test/async_system_stackful_error.cpp
/home/yulia/boost_1_69_0/libs/process/test/async_system_fail.cpp
/home/yulia/boost_1_69_0/libs/process/test/async_pipe.cpp
/home/yulia/boost_1_69_0/libs/process/test/async_system_stackless.cpp
/home/yulia/boost_1_69_0/libs/phoenix/example/adapted_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/ReadHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/BufferedHandshakeHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/Handler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/ConnectHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/IteratorConnectHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/SignalHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/MutableBufferSequence.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/AcceptHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/ConstBufferSequence.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/ResolveHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/RangeConnectHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/MoveAcceptHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/ShutdownHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/WaitHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/HandshakeHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/requirements/WriteHandler.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/tutorial.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/reference.xsl
/home/yulia/boost_1_69_0/libs/asio/doc/using.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/other_protocols.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/signals.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/cpp2011.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/ssl.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/coroutines_ts.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/buffers.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/coroutine.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/basics.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/posix.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/allocation.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/line_based.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/spawn.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/protocols.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/overview/strands.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/examples.qbk
/home/yulia/boost_1_69_0/libs/asio/doc/reference.qbk
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/ssl/client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/ssl/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/timers/time_t_timer.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/serialization/client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/serialization/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/serialization/connection.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/chat/chat_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/chat/posix_chat_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/chat/chat_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/icmp/ipv4_header.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/icmp/ping.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/buffers/reference_counted.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/nonblocking/third_party_lib.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/fork/process_per_connection.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/fork/daemon.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/echo/async_tcp_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/echo/blocking_tcp_echo_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/echo/async_udp_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/echo/blocking_udp_echo_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/echo/blocking_udp_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/echo/blocking_tcp_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/spawn/parallel_grep.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/spawn/echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/windows/transmit_file.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer3/timer.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer1/timer.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime2/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer4/timer.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime5/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime1/client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime7/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime4/client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer2/timer.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime_dox.txt
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime6/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime3/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer5/timer.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer_dox.txt
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/iostreams/daytime_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/iostreams/daytime_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/iostreams/http_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/local/iostream_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/local/stream_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/local/connect_pair.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/local/stream_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/socks4/socks4.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/socks4/sync_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server4/main.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server4/server.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server4/reply.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server4/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server4/request_parser.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server4/reply.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server3/server.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server3/reply.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server3/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server3/connection.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server3/connection.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server3/reply.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/client/sync_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/client/async_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server2/io_context_pool.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server2/server.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server2/reply.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server2/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server2/connection.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server2/connection.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server2/io_context_pool.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server2/reply.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server/server.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server/reply.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server/connection.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server/connection.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/http/server/reply.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/porthopper/client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/porthopper/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/porthopper/protocol.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/timeouts/blocking_udp_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/timeouts/blocking_tcp_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/timeouts/blocking_token_tcp_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/timeouts/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/timeouts/async_tcp_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/allocation/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/multicast/sender.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/multicast/receiver.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/services/daytime_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/services/logger_service.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/services/logger_service.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/services/basic_logger.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp03/invocation/prioritised_handlers.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/ssl/client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/ssl/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/timers/time_t_timer.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/chat/chat_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/chat/chat_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/buffers/reference_counted.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/executors/bank_account_1.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/executors/priority_scheduler.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/executors/pipeline.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/executors/actor.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/executors/bank_account_2.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/executors/fork_join.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/nonblocking/third_party_lib.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/fork/process_per_connection.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/fork/daemon.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/echo/async_tcp_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/echo/blocking_tcp_echo_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/echo/async_udp_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/echo/blocking_udp_echo_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/echo/blocking_udp_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/echo/blocking_tcp_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/spawn/parallel_grep.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/spawn/echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/operations/composed_3.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/operations/composed_1.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/operations/composed_4.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/operations/composed_5.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/operations/composed_2.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/handler_tracking/async_tcp_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/handler_tracking/custom_tracking.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/iostreams/http_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/local/iostream_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/local/stream_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/local/connect_pair.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/local/stream_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/socks4/socks4.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/socks4/sync_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/http/server/server.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/http/server/reply.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/http/server/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/http/server/connection.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/http/server/connection.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/http/server/reply.hpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/timeouts/blocking_udp_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/timeouts/blocking_tcp_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/timeouts/blocking_token_tcp_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/timeouts/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/timeouts/async_tcp_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/futures/daytime_client.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/allocation/server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/multicast/sender.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/multicast/receiver.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp11/invocation/prioritised_handlers.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp17/coroutines_ts/double_buffered_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp17/coroutines_ts/chat_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp17/coroutines_ts/range_based_for.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp17/coroutines_ts/refactored_echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/example/cpp17/coroutines_ts/echo_server.cpp
/home/yulia/boost_1_69_0/libs/asio/test/buffered_stream.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ssl/stream.cpp
/home/yulia/boost_1_69_0/libs/asio/test/strand.cpp
/home/yulia/boost_1_69_0/libs/asio/test/read_until.cpp
/home/yulia/boost_1_69_0/libs/asio/test/generic/stream_protocol.cpp
/home/yulia/boost_1_69_0/libs/asio/test/generic/seq_packet_protocol.cpp
/home/yulia/boost_1_69_0/libs/asio/test/generic/raw_protocol.cpp
/home/yulia/boost_1_69_0/libs/asio/test/generic/datagram_protocol.cpp
/home/yulia/boost_1_69_0/libs/asio/test/coroutine.cpp
/home/yulia/boost_1_69_0/libs/asio/test/read_at.cpp
/home/yulia/boost_1_69_0/libs/asio/test/serial_port.cpp
/home/yulia/boost_1_69_0/libs/asio/test/deadline_timer.cpp
/home/yulia/boost_1_69_0/libs/asio/test/streambuf.cpp
/home/yulia/boost_1_69_0/libs/asio/test/buffered_read_stream.cpp
/home/yulia/boost_1_69_0/libs/asio/test/system_timer.cpp
/home/yulia/boost_1_69_0/libs/asio/test/buffered_write_stream.cpp
/home/yulia/boost_1_69_0/libs/asio/test/latency/udp_server.cpp
/home/yulia/boost_1_69_0/libs/asio/test/latency/tcp_client.cpp
/home/yulia/boost_1_69_0/libs/asio/test/latency/tcp_server.cpp
/home/yulia/boost_1_69_0/libs/asio/test/latency/udp_client.cpp
/home/yulia/boost_1_69_0/libs/asio/test/unit_test.hpp
/home/yulia/boost_1_69_0/libs/asio/test/is_write_buffered.cpp
/home/yulia/boost_1_69_0/libs/asio/test/windows/object_handle.cpp
/home/yulia/boost_1_69_0/libs/asio/test/windows/stream_handle.cpp
/home/yulia/boost_1_69_0/libs/asio/test/windows/random_access_handle.cpp
/home/yulia/boost_1_69_0/libs/asio/test/windows/overlapped_ptr.cpp
/home/yulia/boost_1_69_0/libs/asio/test/is_read_buffered.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/network_v6.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/network_v4.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/tcp.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/v6_only.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/address_v6.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/multicast.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/udp.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/unicast.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/address_v4.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/icmp.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/address.cpp
/home/yulia/boost_1_69_0/libs/asio/test/ip/host_name.cpp
/home/yulia/boost_1_69_0/libs/asio/test/buffers_iterator.cpp
/home/yulia/boost_1_69_0/libs/asio/test/serial_port_base.cpp
/home/yulia/boost_1_69_0/libs/asio/test/write.cpp
/home/yulia/boost_1_69_0/libs/asio/test/archetypes/deprecated_async_ops.hpp
/home/yulia/boost_1_69_0/libs/asio/test/archetypes/async_ops.hpp
/home/yulia/boost_1_69_0/libs/asio/test/local/stream_protocol.cpp
/home/yulia/boost_1_69_0/libs/asio/test/local/connect_pair.cpp
/home/yulia/boost_1_69_0/libs/asio/test/local/datagram_protocol.cpp
/home/yulia/boost_1_69_0/libs/asio/test/socket_base.cpp
/home/yulia/boost_1_69_0/libs/asio/test/io_context.cpp
/home/yulia/boost_1_69_0/libs/asio/test/use_future.cpp
/home/yulia/boost_1_69_0/libs/asio/test/write_at.cpp
/home/yulia/boost_1_69_0/libs/asio/test/buffer.cpp
/home/yulia/boost_1_69_0/libs/asio/test/signal_set.cpp
/home/yulia/boost_1_69_0/libs/asio/test/posix/stream_descriptor.cpp
/home/yulia/boost_1_69_0/libs/asio/test/read.cpp
/home/yulia/boost_1_69_0/libs/asio/test/error.cpp
/home/yulia/boost_1_69_0/libs/asio/test/connect.cpp
/home/yulia/boost_1_69_0/boost/log/sinks/syslog_backend.hpp
/home/yulia/boost_1_69_0/boost/beast/http/impl/serializer.ipp
/home/yulia/boost_1_69_0/boost/beast/http/impl/file_body_win32.ipp
/home/yulia/boost_1_69_0/boost/beast/http/impl/read.ipp
/home/yulia/boost_1_69_0/boost/beast/http/impl/basic_parser.ipp
/home/yulia/boost_1_69_0/boost/beast/http/impl/write.ipp
/home/yulia/boost_1_69_0/boost/beast/http/impl/chunk_encode.ipp
/home/yulia/boost_1_69_0/boost/beast/http/impl/fields.ipp
/home/yulia/boost_1_69_0/boost/beast/http/span_body.hpp
/home/yulia/boost_1_69_0/boost/beast/http/parser.hpp
/home/yulia/boost_1_69_0/boost/beast/http/buffer_body.hpp
/home/yulia/boost_1_69_0/boost/beast/http/fields.hpp
/home/yulia/boost_1_69_0/boost/beast/http/detail/chunk_encode.hpp
/home/yulia/boost_1_69_0/boost/beast/http/read.hpp
/home/yulia/boost_1_69_0/boost/beast/http/string_body.hpp
/home/yulia/boost_1_69_0/boost/beast/http/write.hpp
/home/yulia/boost_1_69_0/boost/beast/http/basic_dynamic_body.hpp
/home/yulia/boost_1_69_0/boost/beast/http/basic_file_body.hpp
/home/yulia/boost_1_69_0/boost/beast/http/basic_parser.hpp
/home/yulia/boost_1_69_0/boost/beast/http/vector_body.hpp
/home/yulia/boost_1_69_0/boost/beast/http/type_traits.hpp
/home/yulia/boost_1_69_0/boost/beast/http/chunk_encode.hpp
/home/yulia/boost_1_69_0/boost/beast/http/serializer.hpp
/home/yulia/boost_1_69_0/boost/beast/http/error.hpp
/home/yulia/boost_1_69_0/boost/beast/http/empty_body.hpp
/home/yulia/boost_1_69_0/boost/beast/core/buffers_adapter.hpp
/home/yulia/boost_1_69_0/boost/beast/core/impl/buffers_prefix.ipp
/home/yulia/boost_1_69_0/boost/beast/core/impl/buffers_adapter.ipp
/home/yulia/boost_1_69_0/boost/beast/core/impl/multi_buffer.ipp
/home/yulia/boost_1_69_0/boost/beast/core/impl/static_buffer.ipp
/home/yulia/boost_1_69_0/boost/beast/core/impl/buffers_cat.ipp
/home/yulia/boost_1_69_0/boost/beast/core/impl/buffers_suffix.ipp
/home/yulia/boost_1_69_0/boost/beast/core/impl/buffered_read_stream.ipp
/home/yulia/boost_1_69_0/boost/beast/core/impl/flat_buffer.ipp
/home/yulia/boost_1_69_0/boost/beast/core/impl/handler_ptr.ipp
/home/yulia/boost_1_69_0/boost/beast/core/impl/flat_static_buffer.ipp
/home/yulia/boost_1_69_0/boost/beast/core/impl/read_size.ipp
/home/yulia/boost_1_69_0/boost/beast/core/static_buffer.hpp
/home/yulia/boost_1_69_0/boost/beast/core/detail/bind_handler.hpp
/home/yulia/boost_1_69_0/boost/beast/core/detail/buffers_ref.hpp
/home/yulia/boost_1_69_0/boost/beast/core/detail/type_traits.hpp
/home/yulia/boost_1_69_0/boost/beast/core/multi_buffer.hpp
/home/yulia/boost_1_69_0/boost/beast/core/bind_handler.hpp
/home/yulia/boost_1_69_0/boost/beast/core/ostream.hpp
/home/yulia/boost_1_69_0/boost/beast/core/buffers_cat.hpp
/home/yulia/boost_1_69_0/boost/beast/core/flat_static_buffer.hpp
/home/yulia/boost_1_69_0/boost/beast/core/buffers_suffix.hpp
/home/yulia/boost_1_69_0/boost/beast/core/flat_buffer.hpp
/home/yulia/boost_1_69_0/boost/beast/core/buffers_to_string.hpp
/home/yulia/boost_1_69_0/boost/beast/core/buffered_read_stream.hpp
/home/yulia/boost_1_69_0/boost/beast/core/type_traits.hpp
/home/yulia/boost_1_69_0/boost/beast/core/buffers_prefix.hpp
/home/yulia/boost_1_69_0/boost/beast/websocket/impl/accept.ipp
/home/yulia/boost_1_69_0/boost/beast/websocket/impl/ping.ipp
/home/yulia/boost_1_69_0/boost/beast/websocket/impl/ssl.ipp
/home/yulia/boost_1_69_0/boost/beast/websocket/impl/stream.ipp
/home/yulia/boost_1_69_0/boost/beast/websocket/impl/read.ipp
/home/yulia/boost_1_69_0/boost/beast/websocket/impl/handshake.ipp
/home/yulia/boost_1_69_0/boost/beast/websocket/impl/close.ipp
/home/yulia/boost_1_69_0/boost/beast/websocket/impl/write.ipp
/home/yulia/boost_1_69_0/boost/beast/websocket/impl/teardown.ipp
/home/yulia/boost_1_69_0/boost/beast/websocket/teardown.hpp
/home/yulia/boost_1_69_0/boost/beast/websocket/detail/stream_base.hpp
/home/yulia/boost_1_69_0/boost/beast/websocket/detail/pausation.hpp
/home/yulia/boost_1_69_0/boost/beast/websocket/detail/utf8_checker.hpp
/home/yulia/boost_1_69_0/boost/beast/websocket/detail/mask.hpp
/home/yulia/boost_1_69_0/boost/beast/websocket/detail/frame.hpp
/home/yulia/boost_1_69_0/boost/beast/websocket/stream.hpp
/home/yulia/boost_1_69_0/boost/beast/websocket/ssl.hpp
/home/yulia/boost_1_69_0/boost/beast/websocket/rfc6455.hpp
/home/yulia/boost_1_69_0/boost/beast/websocket/role.hpp
/home/yulia/boost_1_69_0/boost/beast/experimental/test/impl/stream.ipp
/home/yulia/boost_1_69_0/boost/beast/experimental/test/stream.hpp
/home/yulia/boost_1_69_0/boost/beast/experimental/http/impl/icy_stream.ipp
/home/yulia/boost_1_69_0/boost/beast/experimental/http/icy_stream.hpp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/impl/timeout_service.ipp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/impl/timeout_socket.hpp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/impl/flat_stream.ipp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/detail/impl/timeout_service.ipp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/detail/timeout_service.hpp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/detail/flat_stream.hpp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/detail/service_base.hpp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/timeout_service.hpp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/flat_stream.hpp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/ssl_stream.hpp
/home/yulia/boost_1_69_0/boost/beast/experimental/core/timeout_socket.hpp
/home/yulia/boost_1_69_0/boost/process/async.hpp
/home/yulia/boost_1_69_0/boost/process/io.hpp
/home/yulia/boost_1_69_0/boost/process/detail/windows/io_context_ref.hpp
/home/yulia/boost_1_69_0/boost/process/detail/windows/async_out.hpp
/home/yulia/boost_1_69_0/boost/process/detail/windows/async_pipe.hpp
/home/yulia/boost_1_69_0/boost/process/detail/windows/async_in.hpp
/home/yulia/boost_1_69_0/boost/process/detail/traits/async.hpp
/home/yulia/boost_1_69_0/boost/process/detail/async_handler.hpp
/home/yulia/boost_1_69_0/boost/process/detail/posix/sigchld_service.hpp
/home/yulia/boost_1_69_0/boost/process/detail/posix/io_context_ref.hpp
/home/yulia/boost_1_69_0/boost/process/detail/posix/async_out.hpp
/home/yulia/boost_1_69_0/boost/process/detail/posix/async_pipe.hpp
/home/yulia/boost_1_69_0/boost/process/detail/posix/async_in.hpp
/home/yulia/boost_1_69_0/boost/process/system.hpp
/home/yulia/boost_1_69_0/boost/process/async_pipe.hpp
/home/yulia/boost_1_69_0/boost/process/spawn.hpp
/home/yulia/boost_1_69_0/boost/process/async_system.hpp
/home/yulia/boost_1_69_0/boost/asio/raw_socket_service.hpp
/home/yulia/boost_1_69_0/boost/asio/seq_packet_socket_service.hpp
/home/yulia/boost_1_69_0/boost/asio/impl/execution_context.ipp
/home/yulia/boost_1_69_0/boost/asio/impl/buffered_write_stream.hpp
/home/yulia/boost_1_69_0/boost/asio/impl/write_at.hpp
/home/yulia/boost_1_69_0/boost/asio/impl/read.hpp
/home/yulia/boost_1_69_0/boost/asio/impl/write.hpp
/home/yulia/boost_1_69_0/boost/asio/impl/serial_port_base.ipp
/home/yulia/boost_1_69_0/boost/asio/impl/read_until.hpp
/home/yulia/boost_1_69_0/boost/asio/impl/io_context.ipp
/home/yulia/boost_1_69_0/boost/asio/impl/buffered_read_stream.hpp
/home/yulia/boost_1_69_0/boost/asio/impl/spawn.hpp
/home/yulia/boost_1_69_0/boost/asio/impl/read_at.hpp
/home/yulia/boost_1_69_0/boost/asio/impl/connect.hpp
/home/yulia/boost_1_69_0/boost/asio/impl/io_context.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/impl/error.ipp
/home/yulia/boost_1_69_0/boost/asio/ssl/impl/context.ipp
/home/yulia/boost_1_69_0/boost/asio/ssl/impl/context.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/detail/buffered_handshake_op.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/detail/impl/openssl_init.ipp
/home/yulia/boost_1_69_0/boost/asio/ssl/detail/impl/engine.ipp
/home/yulia/boost_1_69_0/boost/asio/ssl/detail/read_op.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/detail/write_op.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/detail/io.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/detail/openssl_init.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/detail/stream_core.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/detail/engine.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/stream.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/rfc2818_verification.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/context.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/stream_base.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/context_base.hpp
/home/yulia/boost_1_69_0/boost/asio/ssl/error.hpp
/home/yulia/boost_1_69_0/boost/asio/executor.hpp
/home/yulia/boost_1_69_0/boost/asio/use_future.hpp
/home/yulia/boost_1_69_0/boost/asio/buffer.hpp
/home/yulia/boost_1_69_0/boost/asio/generic/stream_protocol.hpp
/home/yulia/boost_1_69_0/boost/asio/generic/raw_protocol.hpp
/home/yulia/boost_1_69_0/boost/asio/generic/seq_packet_protocol.hpp
/home/yulia/boost_1_69_0/boost/asio/generic/detail/impl/endpoint.ipp
/home/yulia/boost_1_69_0/boost/asio/generic/detail/endpoint.hpp
/home/yulia/boost_1_69_0/boost/asio/generic/datagram_protocol.hpp
/home/yulia/boost_1_69_0/boost/asio/generic/basic_endpoint.hpp
/home/yulia/boost_1_69_0/boost/asio/ts/netfwd.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_serial_port.hpp
/home/yulia/boost_1_69_0/boost/asio/buffered_write_stream.hpp
/home/yulia/boost_1_69_0/boost/asio/serial_port.hpp
/home/yulia/boost_1_69_0/boost/asio/socket_acceptor_service.hpp
/home/yulia/boost_1_69_0/boost/asio/is_executor.hpp
/home/yulia/boost_1_69_0/boost/asio/write_at.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_signal_set.hpp
/home/yulia/boost_1_69_0/boost/asio/execution_context.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_socket_send_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_mutex.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winrt_resolver_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/buffer_sequence_adapter.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/descriptor_ops.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/eventfd_select_interrupter.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_iocp_io_context.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/posix_tss_ptr.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_tss_ptr.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_object_handle_service.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/posix_event.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/scheduler.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/reactive_descriptor_service.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/epoll_reactor.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/socket_ops.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/winrt_timer_scheduler.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/dev_poll_reactor.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_iocp_serial_port_service.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/handler_tracking.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/strand_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/strand_service.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/kqueue_reactor.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/signal_set_service.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/select_reactor.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/strand_executor_service.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/service_registry.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/throw_error.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/resolver_service_base.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/posix_thread.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/posix_mutex.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/reactive_socket_service_base.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_thread.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/buffer_sequence_adapter.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_iocp_io_context.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/select_reactor.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_mutex.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/winrt_ssocket_service_base.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_event.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_iocp_handle_service.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_iocp_socket_service_base.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/pipe_select_interrupter.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/winsock_init.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/win_static_mutex.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/socket_select_interrupter.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/winrt_timer_scheduler.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/reactive_serial_port_service.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/impl/dev_poll_reactor.ipp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_socket_recvfrom_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/resolver_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_socket_sendto_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_wait_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/wait_handler.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/posix_static_mutex.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/resolve_endpoint_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/null_socket_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/null_mutex.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_socket_connect_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_null_buffers_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/is_buffer_sequence.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/wince_thread.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_handle_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_overlapped_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winrt_timer_scheduler.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/dev_poll_reactor.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_socket_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_socket_recv_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_serial_port_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winsock_init.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winrt_socket_connect_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/deadline_timer_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/strand_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/null_static_mutex.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_socket_recvmsg_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_handle_read_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/conditionally_enabled_event.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_socket_service_base.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/descriptor_write_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_socket_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_socket_accept_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/std_static_mutex.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winrt_socket_recv_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/signal_set_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/select_reactor.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/posix_mutex.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/resolve_query_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_handle_write_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/descriptor_ops.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/completion_handler.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_socket_service_base.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_null_buffers_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/scheduler.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/conditionally_enabled_mutex.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winapp_thread.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/service_registry.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/handler_tracking.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/handler_type_requirements.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/std_mutex.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/timer_queue.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/epoll_reactor.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_descriptor_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_socket_recv_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/signal_handler.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winrt_utils.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_socket_accept_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_io_context.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_socket_recvmsg_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winrt_ssocket_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/resolver_service_base.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_wait_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winrt_socket_send_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winrt_resolve_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/string_view.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/handler_alloc_helpers.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/buffered_stream_storage.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/null_thread.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winrt_ssocket_service_base.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/kqueue_reactor.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_socket_send_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_serial_port_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/winrt_async_manager.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_socket_connect_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/consuming_buffers.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/thread_group.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/socket_option.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_static_mutex.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactor_op_queue.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/handler_cont_helpers.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_iocp_overlapped_ptr.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/noncopyable.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/descriptor_read_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/reactive_socket_recvfrom_op.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/win_object_handle_service.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/handler_invoke_helpers.hpp
/home/yulia/boost_1_69_0/boost/asio/detail/null_reactor.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_streambuf.hpp
/home/yulia/boost_1_69_0/boost/asio/deadline_timer_service.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_stream_socket.hpp
/home/yulia/boost_1_69_0/boost/asio/read.hpp
/home/yulia/boost_1_69_0/boost/asio/thread_pool.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/overlapped_ptr.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/random_access_handle_service.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/basic_object_handle.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/stream_handle.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/basic_handle.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/random_access_handle.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/basic_random_access_handle.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/object_handle.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/overlapped_handle.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/stream_handle_service.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/object_handle_service.hpp
/home/yulia/boost_1_69_0/boost/asio/windows/basic_stream_handle.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/network_v6.ipp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/host_name.ipp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/address_v4.ipp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/network_v6.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/address_v6.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/network_v4.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/address.ipp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/basic_endpoint.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/address_v4.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/address_v6.ipp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/address.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/impl/network_v4.ipp
/home/yulia/boost_1_69_0/boost/asio/ip/basic_resolver_iterator.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/resolver_service.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/basic_resolver_query.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/unicast.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/v6_only.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/network_v6.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/detail/impl/endpoint.ipp
/home/yulia/boost_1_69_0/boost/asio/ip/detail/endpoint.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/detail/socket_option.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/address_v6.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/basic_resolver_entry.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/network_v4.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/basic_resolver_results.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/icmp.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/udp.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/basic_endpoint.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/tcp.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/multicast.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/basic_resolver.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/address_v4.hpp
/home/yulia/boost_1_69_0/boost/asio/ip/address.hpp
/home/yulia/boost_1_69_0/boost/asio/write.hpp
/home/yulia/boost_1_69_0/boost/asio/signal_set_service.hpp
/home/yulia/boost_1_69_0/boost/asio/placeholders.hpp
/home/yulia/boost_1_69_0/boost/asio/local/stream_protocol.hpp
/home/yulia/boost_1_69_0/boost/asio/local/detail/impl/endpoint.ipp
/home/yulia/boost_1_69_0/boost/asio/local/detail/endpoint.hpp
/home/yulia/boost_1_69_0/boost/asio/local/datagram_protocol.hpp
/home/yulia/boost_1_69_0/boost/asio/local/basic_endpoint.hpp
/home/yulia/boost_1_69_0/boost/asio/local/connect_pair.hpp
/home/yulia/boost_1_69_0/boost/asio/coroutine.hpp
/home/yulia/boost_1_69_0/boost/asio/waitable_timer_service.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_socket_iostream.hpp
/home/yulia/boost_1_69_0/boost/asio/async_result.hpp
/home/yulia/boost_1_69_0/boost/asio/completion_condition.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_io_object.hpp
/home/yulia/boost_1_69_0/boost/asio/serial_port_service.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_deadline_timer.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_seq_packet_socket.hpp
/home/yulia/boost_1_69_0/boost/asio/buffers_iterator.hpp
/home/yulia/boost_1_69_0/boost/asio/read_until.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_waitable_timer.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_raw_socket.hpp
/home/yulia/boost_1_69_0/boost/asio/datagram_socket_service.hpp
/home/yulia/boost_1_69_0/boost/asio/buffered_read_stream.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_socket_acceptor.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_socket.hpp
/home/yulia/boost_1_69_0/boost/asio/posix/basic_stream_descriptor.hpp
/home/yulia/boost_1_69_0/boost/asio/posix/descriptor.hpp
/home/yulia/boost_1_69_0/boost/asio/posix/basic_descriptor.hpp
/home/yulia/boost_1_69_0/boost/asio/posix/stream_descriptor.hpp
/home/yulia/boost_1_69_0/boost/asio/posix/stream_descriptor_service.hpp
/home/yulia/boost_1_69_0/boost/asio/posix/descriptor_base.hpp
/home/yulia/boost_1_69_0/boost/asio/spawn.hpp
/home/yulia/boost_1_69_0/boost/asio/io_context_strand.hpp
/home/yulia/boost_1_69_0/boost/asio/socket_base.hpp
/home/yulia/boost_1_69_0/boost/asio/signal_set.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_datagram_socket.hpp
/home/yulia/boost_1_69_0/boost/asio/error.hpp
/home/yulia/boost_1_69_0/boost/asio/uses_executor.hpp
/home/yulia/boost_1_69_0/boost/asio/basic_socket_streambuf.hpp
/home/yulia/boost_1_69_0/boost/asio/buffered_stream.hpp
/home/yulia/boost_1_69_0/boost/asio/read_at.hpp
/home/yulia/boost_1_69_0/boost/asio/connect.hpp
/home/yulia/boost_1_69_0/boost/asio/io_context.hpp
/home/yulia/boost_1_69_0/boost/asio/handler_invoke_hook.hpp
/home/yulia/boost_1_69_0/boost/asio/experimental/impl/co_spawn.hpp
/home/yulia/boost_1_69_0/boost/asio/experimental/impl/detached.hpp
/home/yulia/boost_1_69_0/boost/asio/experimental/detached.hpp
/home/yulia/boost_1_69_0/boost/asio/stream_socket_service.hpp

### 8. Компиляция Boost

`cd ~/boost_1_69_0`
`./bootstrap.sh`
`./b2`

### 9. Статические библиотеки

`mkdir -p ~/boost_libs`
`find ~/boost_1_69_0 -name "*.a" -exec cp {} ~/boost_libs/ \;`

Библиотеки скопированы в ~/boost_libs

### 10. Размер каждого файла и топ-10 самых тяжёлых

`du -sh ~/boost_libs/* 2>/dev/null | sort -rh | head -10`

**Результат:**
- 4,5M	/home/yulia/boost_libs/libboost_wave.a
- 2,7M	/home/yulia/boost_libs/libboost_regex.a
- 2,2M	/home/yulia/boost_libs/libboost_unit_test_framework.a
- 2,2M	/home/yulia/boost_libs/libboost_test_exec_monitor.a
- 2,0M	/home/yulia/boost_libs/libboost_locale.a
- 1,5M	/home/yulia/boost_libs/libboost_program_options.a
- 1,2M	/home/yulia/boost_libs/libboost_serialization.a
- 824K	/home/yulia/boost_libs/libboost_graph.a
- 776K	/home/yulia/boost_libs/libboost_wserialization.a
- 400K	/home/yulia/boost_libs/libboost_filesystem.a
