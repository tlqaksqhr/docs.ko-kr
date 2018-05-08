### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>이제 ObjectContext.Translate와 ObjectContext.ExecuteStoreQuery가 열거형 형식을 지원합니다.

|   |   |
|---|---|
|설명|.NET Framework 4.0에서는 <code>ObjectContext.Translate</code> 및 <code>ObjectContext.ExecuteStoreQuery</code> 메서드의 제네릭 매개 변수 <code>T</code>가 열거형일 수 없었습니다. 이제 이 시나리오가 지원됩니다.|
|제안 해결 방법|.NET Framework 4.0의 열거형 형식에서 좌표 이동 또는 ExecuteStoreQuery가 호출되면 ‘0’이 반환되었습니다. 해당 동작이 필요한 경우 호출은 상수 0(또는 열거형 해당 항목)으로 대체되어야 합니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|

