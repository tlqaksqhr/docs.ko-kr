### <a name="multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>단일 TableLayoutPanel 셀에 있는 여러 항목이 다시 배열될 수 있습니다.

|   |   |
|---|---|
|설명|.NET Framework 4.5에서 여러 항목이 동일한 <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name> 셀에 배치되면 .NET Framework 4.0과 다른 순서로 표시될 수 있습니다.|
|제안 해결 방법|이 동작은 .NET Framework 4.5에 대한 서비스 업데이트에서 되돌려졌습니다. 이 문제를 해결하려면 .NET Framework 4.5를 업데이트하거나 .NET Framework 4.5.1 이상으로 업그레이드하십시오. 또는 동일한 <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name> 셀에서 여러 항목이 모호하지 않도록 방지합니다.|
|범위|부|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Windows.Forms.TableLayoutControlCollection.Add(System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32)?displayProperty=nameWithType></li></ul>|
|분석기|<ul><li>CD0098</li></ul>|

