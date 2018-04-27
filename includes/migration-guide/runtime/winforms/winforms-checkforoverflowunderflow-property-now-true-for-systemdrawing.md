### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>WinForm의 CheckForOverflowUnderflow 속성은 이제 System.Drawing에 대해 true입니다.

|   |   |
|---|---|
|설명|System.Drawing.dll 어셈블리의 CheckForOverflowUnderflow 속성이 true로 설정됩니다.|
|제안 해결 방법|이전에 오버플로가 발생했을 때는 결과가 자동으로 잘렸습니다. 이제 <xref:System.OverflowException?displayProperty=name> 예외가 throw됩니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|

