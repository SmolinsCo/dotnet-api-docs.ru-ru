### <a name="accessibility-improvements-in-windows-workflow-foundation-wf-workflow-designer"></a>Улучшения специальных возможностей в конструкторе рабочих процессов Windows Workflow Foundation (WF)

|   |   |
|---|---|
|Подробные сведения|В конструкторе рабочих процессов Windows Workflow Foundation (WF) реализован ряд улучшений, касающихся использования специальных возможностей. К этим улучшениям относятся следующие:<ul><li>Для некоторых элементов управления изменена последовательность табуляции при переходе слева направо и сверху вниз:</li><li>Окно инициализации корреляции для установки данных корреляции для действия <xref:System.ServiceModel.Activities.InitializeCorrelation></li><li>Окно определения содержания для действий <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply></li><li>Большее число функций доступно с клавиатуры:</li><li>При редактировании свойств действия группы свойств можно сворачивать с помощью клавиатуры в том случае, если они впервые получают фокус.</li><li>Значки предупреждений теперь доступны с клавиатуры.</li><li>Кнопка дополнительных свойств в окне свойств теперь доступна с клавиатуры.</li><li>Пользователи теперь могут с помощью клавиатуры получать доступ к элементам заголовка в областях аргументов и переменных в конструкторе рабочих процессов.</li><li>Улучшена видимость находящихся в фокусе элементов, например в следующих случаях:</li><li>Добавление строк в сетки данных, используемые конструктором рабочих процессов и конструкторами действий.</li><li>Переход по клавише TAB между полями в действиях <xref:System.ServiceModel.Activities.ReceiveReply> и <xref:System.ServiceModel.Activities.SendReply>.</li><li>Установка значений по умолчанию для переменных или аргументов</li><li>Средства чтения с экрана теперь правильно распознают следующие объекты:</li><li>Точки останова, установленные в конструкторе рабочих процессов.</li><li>Действия <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> и <xref:System.ServiceModel.Activities.CorrelationScope>.</li><li>Содержимое действия <xref:System.ServiceModel.Activities.Receive>.</li><li>Целевой тип действия <xref:System.Activities.Statements.InvokeMethod>.</li><li>Поле со списком "Исключение" и раздел Finally действия <xref:System.Activities.Statements.TryCatch>.</li><li>Поле со списком "Тип сообщения", разделитель в окне "Добавить инициализаторы корреляции", окно "Определение содержимого", а также окно "Определение корреляции" в действиях сообщений (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply>).</li><li>Переходы и назначения переходов конечного автомата.</li><li>Заметки и соединители для действий <xref:System.Activities.Statements.FlowDecision>.</li><li>Контекстные меню действий, вызываемые при щелчке правой кнопкой мыши.</li><li>Редакторы значений свойств, кнопка "Очистить условия поиска", кнопки сортировки "По категории" и "По алфавиту", а также диалоговое окно "Редактор выражений" в сетке свойств.</li><li>Величина масштаба в конструкторе рабочих процессов.</li><li>Разделитель в действиях <xref:System.Activities.Statements.Parallel> и <xref:System.Activities.Statements.Pick>.</li><li>Действие <xref:System.Activities.Statements.InvokeDelegate>.</li><li>Окно "Выбор типов" для действий словаря (<code>Microsoft.Activities.AddToDictionary&lt;TKey,TValue&gt;</code>, <code>Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue&gt;</code> и т. д.).</li><li>Окно поиска и выбора типа .NET.</li><li>Элемент иерархической навигации в конструкторе рабочих процессов.</li><li>Пользователи, работающие с темами высокой контрастности, обратят внимание на улучшение видимости многих частей конструктора рабочих процессов и его элементов управления, в том числе повышение контрастности между элементами, а также более заметные поля выбора для элементов, находящихся в фокусе.</li></ul>|
|Предложение|Если в вашем приложении повторно размещается конструктор рабочих процессов, чтобы использовать эти улучшения, необходимо выполнить следующие действия:<ul><li>Выполните повторную компиляцию приложения, чтобы ориентировать его на платформу .NET Framework 4.7.1. По умолчанию эти новые специальные возможности включены.</li><li>Если ваше приложение предназначено для .NET Framework 4.7 или более ранней версии, но выполняется в .NET Framework 4.7.1, вы можете отключить старые функции специальных возможностей, добавив следующий [переключатель AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел <code>&lt;runtime&gt;</code> файла app.config и присвоив ему значение <code>false</code>, как показано в следующем примере.</li></ul><pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, где требуется сохранить предыдущие функции специальных возможностей, можно выбрать прежние функции специальных возможностей, явно установив этот переключатель AppContext в значение <code>true</code>.|
|Область|Дополнительный номер|
|Версия|4.7.1|
|Тип|Изменение целевой платформы|
