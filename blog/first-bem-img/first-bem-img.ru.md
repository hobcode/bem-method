#Хакатон по БЭМ: проект «Картинки» (src2img)

<img style="float: right" src="https://dl.dropboxusercontent.com/u/1122837/src2img.png" alt="фотография офиса Яндекса в Санкт-Петербурге" width="200" title="BEMup в Санкт-Петербурге" />

Привет, меня зовут [Алексей Кондратов](https://ru.bem.info/authors/kondratov-alexey) и я представлял на хакатоне проект «[src2img](http://src2img.com/)».

## Предыстория

Забегая вперед: на хакатоне мы сделали сервис для сохранения подсвеченного кода в виде картинки. Как так получилось, что мы решили делать именно этот проект?

В сентябре 2014 года я выступал с докладом на [BEMup'е в Питере](https://ru.bem.info/talks/bemup-spb-2014/) и, делая презентацию, привычными движениями делал скриншоты своего любимого текстового редактора, чтобы вставить картинку с подсвеченными примерами кода.

Потом выяснялось, что моя стандартная темная тема плохо читается на слайде. Пришлось снова сделать скриншот, но уже в другой цветовой схеме. Иногда в выделенную область попадали элементы интерфейса, я опять переделывал. Иногда находил ошубку и... Ну, вы поняли :)

Само собой, этот процесс показался мне весьма несовершенным, и я стал искать что-то готовое. Хотелось просто сделать «Ctrl + C» нужного куска кода, потом «Ctrl + V» в форму, выбрать тему и скачать готовую картинку размером ровно по коду.

Когда я узнал про хакатон, предложил Леше [@rndD](https://github.com/rndD) поучаствовать, и он согласился. У нас было несколько идей, но в результате мы остановились на сервисе с картинками.

## Подготовка

Мы были на 100% уверены, что успеем все сделать и запустить готовый сервис вдвоем за отведенное время.

Чтобы на хакатоне не заниматься неинтересной рутиной, мы сделали несколько подготовительных действий:
  * Зарегистрировали домен [src2img.com](http://src2img.com)
  * Засетапили виртуалку на DigitalOcean
  * Создали репозиторий [team411/src2img](https://github.com/team411/src2img)
  * Настроили DNS
  * и повесили заглушку с картинкой

Изначально мы не были уверены, что сможем обойтись без бэкенда, поэтому хотели использовать на сервере phantom.js для отрисовки скриншотов.

В остальном, планировалось использовать стандартный БЭМ-стэк: [enb](https://ru.bem.info/tools/bem/enb-bem-examples/), [bem-core](https://ru.bem.info/libs/bem-core/v2.5.0/), [bem-components](https://ru.bem.info/libs/bem-components/v2/).

![](https://img-fotki.yandex.ru/get/15583/44214498.bc/0_9bbd7_63e86f23_XL.jpg)

## Задачи на хакатон

Задач было не так много. Мы хотели реализовать базовую функциональность, описанную выше.

Решили, что если к нам кто-нибудь еще присоединится, то можно будет докрутить каких-то дополнительных фич и улучшений.

И ура, к нам присоединились еще двое ребят — Дима ([@corpix](https://github.com/corpix)) и Миша ([@restrry](https://github.com/restrry))!

![](https://img-fotki.yandex.ru/get/15595/44214498.bc/0_9bbf9_f5dae655_XL.jpg)

## Работа над проектом

В самом начале мы исследовали тему и выяснили, что для работы базовой функциональности мы сможем обойтись совсем без бэкенда (спасибо библиотеке [html2canvas](https://github.com/niklasvh/html2canvas))! Чтобы проверить это, мы буквально за полчаса сделали рабочий прототип в jsFiddle.

Так как наша команда теперь состояла аж из четырех человек, мы разделили задачи:
 * Мы с Мишей больше занимались клиентскими блоками
 * Леша допиливал сборку и деплоил готовый результат на наш сервер
 * Дима очень сильно помог со сборкой и фризом статики, а потом вообще запилил свой экспериментальный бэкенд на python, в котором он рендерил bemhtml-шаблоны

В процессе работы у нас возникли серьезные проблемы с генератором проектов [generator-bem-stub](https://github.com/bem/generator-bem-stub), который, несмотря на выбранные нами нужные опции, выдавал безумное количество ошибок в шаблонах bh, не собирал весь css и js даже для стандартных блоков из bem-components. Нам пришлось все удалить и скачать готовый project-stub. Это затормозило нас часа на 2-3.

![](https://img-fotki.yandex.ru/get/17918/44214498.bc/0_9bbf8_d81430b0_XL.jpg)

## Результаты

По результатам хакатона мы сделали все, что и планировали, плюс немного вышли за рамки благодаря новым членам команды.

Вот то, что у нас получилось:
 * Работающий сервис — [src2img.com](http://src2img.com)
 * Исходники — [src2img на github](https://github.com/team411/src2img)
 * Экспериментальный python-бэкенд — [src2img-backend на github](https://github.com/team411/src2img-backend)

![](https://img-fotki.yandex.ru/get/15597/44214498.bd/0_9bc2e_3b95b4e4_XL.jpg)

## Впечатления

Я очень рад, что мне удалось поучастовать в этом хакатоне. А еще больше я рад, что к моей команде присоединились такие крутые ребята, и мы смогли вместе реализовать все задуманное :) Без них бы у меня ничего не получилось.

Трудно к чему-либо придраться в организации хакатона, поэтому просто еще раз скажу спасибо организаторам и своей команде.

Было круто! Надеюсь, что это был только первый хакатон по БЭМ!

**Stay BEMed!**

![](https://img-fotki.yandex.ru/get/15565/44214498.bd/0_9bc30_a0c39994_XL.jpg)
