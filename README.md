# Шаблон модуля-задания GraphLabs.

**TaskTemplate** - каркас для новых модулей-заданий на Silverlight.

## Запуск и отладка

Проект можно запускать в двух режимах: в браузере и вне браузера. Принципы запуска и отладки в двух различных режимах существенно отличаются.


**Работа в браузере**

*Запуск*

  1. В первую очередь необходимо в "Solution configurations" установить режим "DebugWithSite"
  2. Далее в "Solution Explorer" открыть "GraphLabs.Tasks.Template". В "Properties" нужно изменить некоторые настройки: в разделе "Debug" необхдимо выбрать "Dynamically generate a test page". 
  3. Для запуска проекта в меню Visual Studio в разделе "Debug" выбрать "Start debugging". В зависимости от выбранного по умолчанию браузера может возникнуть ошибка - см. пункт 2 FAQ.
  
*Отладка*

  Настройка графа осуществляется в файле "Program.cs", в котором можно задать количество вершин и связи между ними.  


**Работа вне браузера**

*Запуск*

  1. Аналогично - в "Solution configurations" установить режим "Debug"
  2. В "Properties" в том же разделе "Debug" выбрать "Out-of-browser application". 
  3. После запуска проекта работа с графом будет возможна в новом окне приложения. 
*Отладка*

  Задать граф можно в файле "MockedWcfServicesConfigurator.cs".
  

## FAQ

* **Q**: При сборке проекта падает ошибка о том, что "выполнение сценариев отключено в этой системе" ("execution of scripts is disabled on this system").
* *A*: Необходимо разрешить выполнение Powershell-скриптов. Для этого, запустите консоль Powershell (x86) с правами администратора, и выполните "Set-ExecutionPolicy Unrestricted"


* **Q**: При сборке проекта выдаёт ошибку "Unable to attach to application '<имя браузера>.exe' (PID: XXXX) using 'DESKTOP-OB7UNSH'. The 32-bit version of the Visual Studio Remote Debugger (MSVSMON.EXE) cannot be used to debug 64-bit processes or 64-bit dumps. Please use the 64-bit version instead."
* *A*: Необходимо изменить браузер в настройках Visual Studio через "Browse with..." или в настройках системы выбрать браузер по умолчанию, например Internet Explorer. 
