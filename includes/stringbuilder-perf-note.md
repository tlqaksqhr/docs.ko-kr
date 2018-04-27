<xref:System.Text.StringBuilder.Chars%2A> 속성에서 문자 기반 인덱싱을 사용하면 다음과 같은 조건 하에서 성능이 매우 느려질 수 있습니다.

- <xref:System.Text.StringBuilder> 인스턴스는 대규모입니다(예: 수만 개의 문자로 구성됩).
- <xref:System.Text.StringBuilder>는 "청크"입니다. 즉, <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>과 같은 메서드에 반복된 호출은 자동으로 개체 <xref:System.Text.StringBuilder.Capacity%2A?displayProperty=nameWithType> 속성을 확장하고 해당 메모리의 새 청크를 할당했습니다.

각 문자 액세스가 인덱싱할 올바른 버퍼를 찾기 위해 연결된 전체 청크 목록을 확인하기 때문에 성능이 심각하게 저하됩니다.

> [!NOTE]
>  대규모 "청크" <xref:System.Text.StringBuilder> 개체의 경우 하나 이하의 문자에 대한 인덱스 기반 액세스에 <xref:System.Text.StringBuilder.Chars%2A> 속성을 사용하면 성능에 미치는 영향이 적습니다. 일반적으로 **0(n)** 개 작업에 영향을 줍니다. <xref:System.Text.StringBuilder> 개체에서 문자를 반복할 때 성능에 상당한 영향이 발생합니다. **O(n^2)** 개 작업에 영향을 줍니다. 

<xref:System.Text.StringBuilder> 개체에서 문자 기반 인덱싱을 사용할 때 성능 문제가 발생하는 경우 다음 방법 중 하나를 사용할 수 있습니다.

- <xref:System.Text.StringBuilder.ToString%2A> 메서드를 호출하여 <xref:System.Text.StringBuilder> 인스턴스를 <xref:System.String>으로 변환한 다음, 문자열의 문자에 액세스합니다.

- 기존 <xref:System.Text.StringBuilder> 개체의 콘텐츠를 크기가 미리 지정된 새로운 <xref:System.Text.StringBuilder> 개체로 복사합니다. 새로운 <xref:System.Text.StringBuilder> 개체가 청크가 아니기 때문에 성능이 향상됩니다. 예:

   ```csharp
   // sbOriginal is the existing StringBuilder object
   var sbNew = new StringBuilder(sbOriginal.ToString(), sbOriginal.Length);
   ```
   ```vb
   ' sbOriginal is the existing StringBuilder object
   Dim sbNew = New StringBuilder(sbOriginal.ToString(), sbOriginal.Length)
   ```
- <xref:System.Text.StringBuilder.%23ctor(System.Int32)> 생성자를 호출하여 <xref:System.Text.StringBuilder> 개체의 초기 용량을 예상된 최대 크기와 대략 동일한 값으로 설정합니다. <xref:System.Text.StringBuilder>가 거의 최대 용량에 도달하더라도 메모리의 전체 블록을 할당합니다.
