Этот репозиторий представляет собой выполнение тестового задания, которое звучало так:

> ### Задача
> Не ожидаем production-ready решения. Сделайте, как кажется правильным, опишите процесс поиска и принятые решения.
> Опишите deployment для веб-приложения в kubernetes в виде yaml-манифеста. Оставляйте в коде комментарии по принятым решениям. Есть следующие вводные:
>
> - у нас мультизональный кластер (три зоны), в котором пять нод
> - приложение требует около 5-10 секунд для инициализации
> - по результатам нагрузочного теста известно, что 4 пода справляются с пиковой нагрузкой
> - на первые запросы приложению требуется значительно больше ресурсов CPU, в дальнейшем потребление ровное в районе 0.1 CPU. По памяти всегда “ровно” в районе 128M memory
> - приложение имеет дневной цикл по нагрузке – ночью запросов на порядки меньше, пик – днём
> - хотим максимально отказоустойчивый deployment
> - хотим минимального потребления ресурсов от этого deployment’а

----

Манифест тестировался на GKE

```
clientVersion:
  buildDate: "2020-09-16T13:41:02Z"
  compiler: gc
  gitCommit: f5743093fd1c663cb0cbc89748f730662345d44d
  gitTreeState: clean
  gitVersion: v1.19.2
  goVersion: go1.15
  major: "1"
  minor: "19"
  platform: linux/amd64
serverVersion:
  buildDate: "2020-09-09T00:57:35Z"
  compiler: gc
  gitCommit: eb94c181eea5290e9da1238db02cfef263542f5f
  gitTreeState: clean
  gitVersion: v1.16.13-gke.401
  goVersion: go1.13.9b4
  major: "1"
  minor: 16+
  platform: linux/amd64
```
