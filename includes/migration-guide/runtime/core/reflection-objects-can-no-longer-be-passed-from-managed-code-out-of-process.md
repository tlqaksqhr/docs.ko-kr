### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>더 이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다

|   |   |
|---|---|
|설명|더이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다. 다음 형식이 영향을 받습니다.<ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><xref:System.Reflection.MemberInfo?displayProperty=name>(및 <xref:System.Reflection.FieldInfo?displayProperty=name>,<xref:System.Reflection.MethodInfo?displayProperty=name>,<xref:System.Type?displayProperty=name> 및 <xref:System.Reflection.TypeInfo?displayProperty=name>을 포함한 파생된 형식)</li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><xref:System.Reflection.ParameterInfo?displayProperty=name>.</li></ul>개체에 대한 <code>IMarshal</code>을 호출하면 <code>E_NOINTERFACE</code>를 반환합니다.|
|제안 해결 방법|마샬링 코드를 리플렉션이 아닌 개체를 사용하도록 업데이트|
|범위|부|
|버전|4.6|
|형식|런타임|

