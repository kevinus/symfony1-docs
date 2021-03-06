﻿Введение
========

*автор Fabien Potencier*

На момент написания этих слов, symfony отпраздновал знаменательную дату –
свой [четвертый день рождения](http://trac.symfony-project.org/changeset/1).
Всего за четыре года, symfony framework вырос и стал одним из наиболее популярных
PHP-фреймворков в мире, питая своей энергией такие сайты как [Delicious](http://sf-to.org/delicious),
[Yahoo Bookmarks](http://sf-to.org/bookmarks) и [Daily Motion](http://sf-to.org/dailymotion).

Но, с недавним релизом symfony 1.4 (ноябрь 2009) мы добрались до конца цикла
(или если угодно, исчерпали возможности развития, подошли к качественному скачку).
Эта книга – прекрасный способ окончить цикл разработки версии 1.xxx и, таким образом,
вы собираетесь прочесть последнюю книгу о symfony 1го бранча, которая будет опубликована
проектной группой symfony. Наша следующая книга будет скорее всего о symfony 2.0,
который ожидается в конце 2010 года.

Зачем нужна еще одна книга?
---------------------------

Мы уже опубликовали две книги о symfony 1.3 и 1.4: “[Practical symfony](http://books.sensiolabs.com/book/9782918390169)”
и “The symfony reference guide[(http://books.sensiolabs.com/book/9782918390145)]“.
Первая из них – отличный способ начать изучение symfony, так как вы изучаете основы
его через разработку реального проекта шаг за шагом. Другая же книга – это справочник,
который содержит бОльшую часть информации о конфигурировании symfony, которая вам
может понадобиться в повседневной разработке.

“More with symfony” (она же “The symfony 2009 Advent Calendar”) – это книга, о более
продвинутых аспектах symfony-разработки. Это не та книга, которую нужно читать
в первую очередь при знакомстве с symfony, но она будет полезна тем, кто уже разработал
несколько небольших проектов на symfony. Если вы хотите узнать как устроен symfony,
как он работает, или же вы хотите расширить возможности фреймворка для выполнения
различных специфических задач – эта книга для вас. Таким образом, “More with symfony”
это то что вам нужно, чтобы поднять свои навыки по symfony на новый качественный уровень.

Так как книга построена как набор руководств по различным направлениям,
вы вольны читать ее с любой главы и в любом порядке, в зависимости от ваших
потребностей или интересов.

Об этой книге
-------------

Эта книга особенная, потому что она написана сообществом и для сообщества.
Масса людей вложило свой труд в ее написание, начиная от авторов и заканчивая
переводчиками, корректорами; множество их усилий слились в этой книге.

Эта книга будет опубликована как минимум на пяти языках (английском, французском,
испанском, итальянском, японском). Мы бы не смогли этого сделать без самоотверженной
работы нашей команды переводчиков.

Эта книга появилась на свет благодаря духу open source и она публикуется
под лицензией open source. Уже один этот факт меняет все.
Это означает что никто не оплачивает работу над книгой: все, кто работал над ее
созданием, трудились в поте лиц потому что они этого хотели. Каждый, кто хотел
поделиться своими знаниями, получить что-то от сообщества, помочь распространению
информации о symfony и, наконец, получить удовольствие и стать знаменитыми.

Эта книга была написана десятью авторами, которые либо ежедневно используют
symfony изо дня в день в качестве разработчиков, либо менеджерами проектов.
Они обладают глубокими познаниями о фреймворке и они постарались поделиться
своими знаниями и опытом.

Выражения благодарности
-----------------------

Когда я начал подумывать о написании еще одной книги о symfony в августе 2009 года,
у меня сразу возникла сумасшедшая идея: а что если написать книгу за два месяца
и опубликовать ее сразу на пяти языках! Конечно, вовлечение сообщества в проект
таких масштабов было просто необходимо. Я начал рассказывать об этой идее в ходе
PHP-конференции в Японии и в считанные часы японская команда переводчиков была
готова к работе. Это было просто невероятно! Реакция авторов и переводчиков в
равной степени обнадеживала и спустя немного времени, проект “More with symfony”
был запущен.

Я хочу поблагодарить всех, кто принял участие тем или иным образом во время
создания этой книги:

Ryan Weaver, Geoffrey Bachelet, Hugo Hamon, Jonathan Wage, Thomas Rabaix,
Fabrice Bernhard, Kris Wallsmith, Stefan Koopmanschap, Laurent Bonnet,
Julien Madelin, Franck Bodiot, Javier Eguiluz, Nicolas Ricci, Fabrizio Pucci,
Francesco Fullone, Massimiliano Arione, Daniel Londero, Xavier Briand,
Guillaume Bretou, Akky Akimoto, Hidenori Goto, Hideki Suzuki, Katsuhiro Ogawa,
 Kousuke Ebihara, Masaki Kagaya, Masao Maeda, Shin Ohno, Tomohiro Mitsumune,
и Yoshihiro Takahara.

Прежде чем начать
-----------------

Эта книга была написана для версий symfony 1.3 и 1.4. Написание книги для
двух версий одного и того же программного обеспечения – явление несколько необычное,
в этой секции будут даны разъяснения по поводу основных различий этих двух версий,
чтобы вы могли выбрать одну из них для ваших проектов.

Обе версии symfony 1.3 и 1.4 вышли в релиз примерно в одно и то же время (в конце 2009 года).
Собственно говоря, обе они имеют **абсолютно одинаковый набор фич**.
Единственное отличие этих двух версий в том, как они поддерживают обратную
совместимость с более ранними версиями symfony.

Symfony 1.3 это релиз который вам нужен, если нужно делать upgrade для существующего проекта,
который работает со старой версией symfony (1.0, 1.1, 1.2). Он содержит слой для
обратной совместимости и все фичи, которые устарели и не рекомендованы к применению
во время отладки и стабилизации ветки 1.3. Это означает, что апгрейд будет простым и безопасным.

Если сегодня вы начинаете новый проект, вы должны использовать symfony 1.4.
Эта версия имеет те же возможности что и 1.3, но все устаревшие фичи, включая
слои для обеспечения обратной совместимости были удалены. Эта версия более “чистая”
с точки зрения кода и немного более быстрая по сравнению с 1.3. Другой плюс от
использования symfony 1.4 заключается в более длительной поддержке этой версии –
она будет поддерживаться три года (до ноября 2012 года).

Конечно же, вы можете мигрировать свои проекты на 1.3 и затем понемногу модифицировать
ваш код, удаляя устаревшие фичи и в конечном счете перейти на 1.4 для того чтобы
иметь более длительную поддержку. У вас достаточно времени для планирования,
так как Symfony 1.3 будет поддерживаться в течение года (до ноября 2010 года).

Так как в этой книге не упоминаются устаревшие фичи, все примеры работают идентично
в обеих версиях.
