### <a name="wpf-treeviewitem-must-be-used-within-a-treeview"></a>В TreeView необходимо использовать TreeViewItem WPF

|   |   |
|---|---|
|Подробные сведения|В версии 4.5 было представлено изменение, которое ограничивает использование элементов <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> за пределами <xref:System.Windows.Controls.TreeView?displayProperty=name>. Это происходит в следующих случаях.<ul><li>Визуальный родительский элемент <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> не является панелью. (<xref:System.Windows.Controls.TreeViewItem?displayProperty=name>, созданный для <xref:System.Windows.Controls.TreeView?displayProperty=name>, будет иметь панель в качестве родительского элемента.)</li><li><xref:System.Windows.Controls.TreeViewItem?displayProperty=name> является потомком <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name>, выступающего в виде &quot;узла элементов&quot; для элемента управления "Список" (ListBox, DataGrid, ListView и т. д.). Виртуализацию включать необязательно.</li><li><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> — это прокрутка элемента (<code>ScrollUnit=&quot;Item&quot;</code>).</li><li>Кто-то вызывает <code>VirtualizingStackPanel.MakeVisible(v)</code> для прокрутки элемента <code>v</code> в представлении. Это можно сделать явно или неявно несколькими способами. Возможно, самым распространенным способом является простой щелчок <code>v</code> для перевода в его фокуса.</li><li>Цепочка визуальных родительских элементов от <code>v</code> до <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> проходит через <xref:System.Windows.Controls.TreeViewItem?displayProperty=name>.</li></ul>Другими словами, это происходит в том случае, когда <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> используется вне <xref:System.Windows.Controls.TreeView?displayProperty=name> и пользователь щелкает потомка <xref:System.Windows.Controls.TreeViewItem?displayProperty=name>, чтобы сделать его видимым. Проблема никогда не возникнет, если у <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> отсутствуют имеющие фокус потомки. Пример такой ситуации — <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> является корнем DataTemplate. При возникновении этой проблемы создается исключение InvalidCastException в рамках платформы WPF.|
|Предложение|Будет создано исправление для этой ошибки.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
