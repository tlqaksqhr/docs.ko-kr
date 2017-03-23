---
title: "문자열(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 문자열"
  - "문자열[C#]"
ms.assetid: 21580405-cb25-4541-89d5-037846a38b07
caps.latest.revision: 41
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 41
---
# 문자열(C# 프로그래밍 가이드)
문자열은 값이 텍스트인 <xref:System.String> 형식의 개체입니다.  내부적으로 텍스트는 <xref:System.Char> 개체의 순차적 읽기 전용 컬렉션으로 저장됩니다.  C\# 문자열 끝에는 null 종결 문자가 없습니다. 따라서 C\# 문자열은 포함된 null 문자\('\\0'\)를 제한 없이 포함할 수 있습니다.  문자열의 <xref:System.String.Length%2A> 속성은 유니코드 문자의 수가 아니라 포함된 `Char` 개체의 수를 나타냅니다.  문자열에서 개별 유니코드 코드 포인트에 액세스하려면 <xref:System.Globalization.StringInfo> 개체를 사용합니다.  
  
## string과System.String  
 C\#에서 `string` 키워드는 <xref:System.String>의 별칭입니다.  따라서 `String` 및 `string`은 동일하며 원하는 명명 규칙을 사용할 수 있습니다.  `String` 클래스는 문자열의 안전한 작성, 조작 및 비교에 사용할 수 있는 많은 메서드를 제공합니다.  또한 C\# 언어는 일부 연산자를 오버로드하여 일반적인 문자열 작업을 간편하게 수행할 수 있도록 합니다.  키워드에 대한 자세한 내용은 [string](../../../csharp/language-reference/keywords/string.md)을 참조하십시오.  형식 및 형식 메서드에 대한 자세한 내용은 <xref:System.String>을 참조하십시오.  
  
## 문자열 선언 및 초기화  
 다음 예제처럼 다양한 방식으로 문자열을 선언하고 초기화할 수 있습니다.  
  
 [!code-cs[csProgGuideStrings#1](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_1.cs)]  
  
 문자열을 문자 배열로 초기화할 경우 이외에는 [new](../../../csharp/language-reference/keywords/new-operator.md) 연산자를 사용하여 문자열 개체를 만들지 마십시오.  
  
 <xref:System.String.Empty> 상수 값으로 문자열을 초기화하여 문자열 길이가 0인 <xref:System.String> 개체를 새로 만듭니다.  길이가 0인 문자열의 문자열 리터럴 표현은 ""입니다.  문자열을 [null](../../../csharp/language-reference/keywords/null.md) 대신 <xref:System.String.Empty> 값으로 초기화하면 <xref:System.NullReferenceException> 발생 위험을 줄일 수 있습니다.  문자열에 액세스하기 전에 문자열 값을 확인하려면 <xref:System.String.IsNullOrEmpty%28System.String%29> 메서드를 사용합니다.  
  
## 문자열 개체의 불변성  
 문자열 개체는 한 번 만들어지면 변경할 수 없는 *변경 불가능* 개체입니다.  문자열을 수정하는 것처럼 보이는 모든 <xref:System.String> 메서드 및 C\# 연산자도 실제로는 새 문자열 개체로 결과를 반환합니다.  다음 예제에서 `s1`과 `s2`의 내용이 결합되어 단일 문자열이 만들어질 때, 두 원본 문자열은 변경되지 않습니다.  `+=` 연산자는 결합된 내용을 포함하는 새 문자열을 만듭니다.  새 개체는 `s1` 변수에 할당되고 `s1`에 할당되었던 원래 개체는 해당 개체에 대한 참조를 유지하는 다른 변수가 없으므로 가비지 수집을 위해 해제됩니다.  
  
 [!code-cs[csProgGuideStrings#2](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_2.cs)]  
  
 문자열 "수정"이 실제로는 새 문자열 생성이므로 문자열에 대한 참조를 만들 때 주의해야 합니다.  문자열에 대한 참조를 만든 다음 원래 문자열을 "수정"할 경우 해당 참조는 문자열을 수정할 때 만든 새 개체 대신 원래 개체를 계속해서 가리킵니다.  다음 코드에서는 이러한 동작을 보여 줍니다.  
  
 [!code-cs[csProgGuideStrings#25](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_3.cs)]  
  
 원래 문자열에 대한 검색 및 바꾸기 작업과 같은 수정에 기반하여 새 문자열을 만드는 방법에 대한 자세한 내용은 [방법: 문자열 내용 수정](../../../csharp/programming-guide/strings/how-to-modify-string-contents.md)을 참조하십시오.  
  
## 일반 문자열 및 약어 문자열 리터럴  
 다음 예제에서 볼 수 있는 것처럼, C\#에서 제공하는 이스케이프 문자를 포함해야 하는 경우 일반 문자열 리터럴을 사용합니다.  
  
 [!code-cs[csProgGuideStrings#3](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_4.cs)]  
  
 문자열 텍스트에 파일 경로 등의 백슬래시 문자가 포함되는 경우에는 사용 편의성과 가독성을 향상시킬 수 있도록 약어 문자열을 사용합니다.  약어 문자열은 줄 바꿈 문자를 문자열 텍스트의 일부로 포함하므로 여러 줄 문자열을 초기화하는 데 사용할 수 있습니다.  약어 문자열 내에 인용 부호를 포함하려면 큰따옴표를 사용합니다.  다음 예제에서는 약어 문자열의 몇 가지 일반적인 용도를 보여 줍니다.  
  
 [!code-cs[csProgGuideStrings#4](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_5.cs)]  
  
## 문자열 이스케이프 시퀀스  
  
|이스케이프 시퀀스|문자 이름|유니코드 인코딩|  
|---------------|-----------|--------------|  
|\\'|작은따옴표|0x0027|  
|\\"|큰따옴표|0x0022|  
|\\\\|백슬래시|0x005C|  
|\\0|Null|0x0000|  
|\\a|경고|0x0007|  
|\\b|백스페이스|0x0008|  
|\\f|폼 피드|0x000C|  
|\\n|줄 바꿈|0x000A|  
|\\r|캐리지 리턴|0x000D|  
|\\t|가로 탭|0x0009|  
|\\U|서로게이트 쌍에 대한 유니코드 이스케이프 시퀀스|\\Unnnnnnnn|  
|\\u|유니코드 이스케이프 시퀀스|\\u0041 \= "A"|  
|\\v|세로 탭|0x000B|  
|\\x|가변 길이를 특징으로 하는 "\\u"와 유사한 유니코드 이스케이프 시퀀스|\\x0041 \= "A"|  
  
> [!NOTE]
>  컴파일 타임에 약어 문자열은 동일한 이스케이프 시퀀스를 갖는 보통 문자열로 변환됩니다.  따라서 약어 문자열을 디버거 조사식 창에서 보면 소스 코드의 약어 버전이 아니라 컴파일러가 추가한 이스케이프 문자를 보게 됩니다.  예를 들어 약어 문자열 @"C:\\files.txt"는 조사식 창에 "C:\\\\files.txt"로 나타납니다.  
  
## 형식 문자열  
 형식 문자열은 런타임에 동적으로 내용을 결정할 수 있는 문자열입니다.  정적 <xref:System.String.Format%2A> 메서드를 사용하고 런타임에 다른 값으로 대체될 내용에 해당하는 자리 표시자를 중괄호로 묶는 방법으로 형식 문자열을 만들 수 있습니다.  다음 예제에서는 형식 문자열을 사용하여 루프의 각 반복 결과를 출력합니다.  
  
 [!code-cs[csProgGuideStrings#26](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_6.cs)]  
  
 <xref:System.Console.WriteLine%2A> 메서드의 한 오버로드는 형식 문자열을 매개 변수로 사용합니다.  따라서 메서드를 명시적으로 호출하지 않고 형식 문자열 리터럴을 포함할 수 있습니다.  하지만 <xref:System.Diagnostics.Trace.WriteLine%2A> 메서드를 사용하여 Visual Studio **출력** 창에 디버그 출력을 표시하는 경우에는 <xref:System.Diagnostics.Trace.WriteLine%2A>에 형식 문자열이 아닌 문자열만 사용할 수 있으므로 <xref:System.String.Format%2A> 메서드를 명시적으로 호출해야 합니다.  서식 문자열에 대한 자세한 내용은 [형식 서식 지정](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md)을 참조하십시오.  
  
## 부분 문자열  
 부분 문자열은 문자열에 포함된 임의의 문자 시퀀스입니다.  <xref:System.String.Substring%2A> 메서드를 사용하면 원래 문자열의 일부를 새 문자열로 만들 수 있습니다.  <xref:System.String.IndexOf%2A> 메서드를 사용하면 하나 이상의 부분 문자열 항목을 검색할 수 있습니다.  <xref:System.String.Replace%2A> 메서드를 사용하면 지정된 부분 문자열의 모든 항목을 새 문자열로 바꿀 수 있습니다.  <xref:System.String.Substring%2A> 메서드와 마찬가지로 <xref:System.String.Replace%2A>는 실제로 새 문자열을 반환하고 원래 문자열을 수정하지 않습니다.  자세한 내용은 [방법: 문자열 처리 메서드를 사용하여 문자열 검색](../../../csharp/programming-guide/strings/how-to-search-strings-using-string-methods.md) 및 [방법: 문자열 내용 수정](../../../csharp/programming-guide/strings/how-to-modify-string-contents.md)을 참조하십시오.  
  
 [!code-cs[csProgGuideStrings#7](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_7.cs)]  
  
## 개별 문자 액세스  
 다음 예제에서 볼 수 있는 것처럼, 인덱스 값을 지정하는 배열 표기법을 사용하여 개별 문자에 읽기 전용으로 액세스할 수 있습니다.  
  
 [!code-cs[csProgGuideStrings#9](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_8.cs)]  
  
 <xref:System.String> 메서드가 문자열의 개별 문자를 수정할 수 있는 기능을 제공하지 않는 경우 <xref:System.Text.StringBuilder> 개체를 사용하여 개별 문자를 "현재 위치"에서 수정한 후 <xref:System.Text.StringBuilder> 메서드를 사용하여 결과를 저장하는 새 문자열을 만들 수 있습니다.  다음 예제에서는 원래 문자열을 특정 방식으로 수정한 다음 나중에 사용할 수 있도록 결과를 저장한다고 가정합니다.  
  
 [!code-cs[csProgGuideStrings#8](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_9.cs)]  
  
## Null 문자열 및 빈 문자열  
 빈 문자열은 문자가 들어 있지 않은 <xref:System.String?displayProperty=fullName> 개체의 인스턴스입니다.  빈 문자열은 다양한 프로그래밍 시나리오에서 빈 텍스트 필드를 나타내는 데 종종 사용됩니다.  빈 문자열은 유효한 <xref:System.String?displayProperty=fullName> 개체이므로 빈 문자열에서 메서드를 호출할 수 있습니다.  빈 문자열은 다음과 같이 초기화됩니다.  
  
```  
string s = String.Empty;  
```  
  
 이와 반대로, null 문자열은 <xref:System.String?displayProperty=fullName> 개체의 인스턴스를 참조하지 않으며 null 문자열에서 메서드를 호출하려고 하면 항상 <xref:System.NullReferenceException>이 발생합니다.  그러나 다른 문자열과의 연결 및 비교 연산에서는 null 문자열을 사용할 수 있습니다.  다음 예제에서는 null 문자열을 참조할 때 예외가 throw되는 경우와 그렇지 않은 경우를 보여 줍니다.  
  
 [!code-cs[csProgGuideStrings#27](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_10.cs)]  
  
## 빠른 문자열 생성을 위해 StringBuilder 사용  
 .NET의 문자열 작업은 매우 최적화되어 있어 대부분의 경우 성능에 영향을 미치지 않습니다.  하지만 수백 번이나 수천 번 이상 실행되는 루프 같은 일부 시나리오에서는 문자열 작업이 성능에 영향을 줄 수 있습니다.  <xref:System.Text.StringBuilder> 클래스는 프로그램에서 수행할 문자열 조작 작업이 많을 경우 성능을 향상시켜 주는 문자열 버퍼를 만듭니다.  또한 <xref:System.Text.StringBuilder> 문자열을 사용하면 개별 문자를 다시 할당할 수 있습니다. 이러한 기능은 기본 제공 데이터 형식에서는 지원하지 않습니다.  예를 들어 다음 코드에서는 새 문자열을 만들지 않고 문자열의 내용을 변경합니다.  
  
 [!code-cs[csProgGuideStrings#20](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_11.cs)]  
  
 이 예제에서는 <xref:System.Text.StringBuilder> 개체를 사용하여 숫자 형식의 집합에서 문자열을 만듭니다.  
  
 [!code-cs[csProgGuideStrings#15](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_12.cs)]  
  
## 문자열, 확장 메서드 및 LINQ  
 <xref:System.String> 형식은 <xref:System.Collections.Generic.IEnumerable%601>을 구현하기 때문에 문자열에서 <xref:System.Linq.Enumerable> 클래스에 정의된 확장 메서드를 사용할 수 있습니다.  시각적인 혼란을 피하기 위해 이러한 메서드는 <xref:System.String> 형식에 대한 IntelliSense에서 제외되어 있지만 여전히 사용할 수 있습니다.  또한 문자열에 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 쿼리 식을 사용할 수도 있습니다.  자세한 내용은 [LINQ and Strings](../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)을 참조하십시오.  
  
## 관련 항목  
  
|항목|설명|  
|--------|--------|  
|[방법: 문자열 내용 수정](../../../csharp/programming-guide/strings/how-to-modify-string-contents.md)|문자열 내용을 수정하는 방법을 보여 주는 코드 예제를 제공합니다.|  
|[방법: 여러 문자열 연결](../../../csharp/programming-guide/strings/how-to-concatenate-multiple-strings.md)|`+` 연산자와 `Stringbuilder` 클래스를 사용하여 컴파일 타임과 런타임에 문자열을 조인하는 방법을 보여 줍니다.|  
|[방법: 문자열 비교](../../../csharp/programming-guide/strings/how-to-compare-strings.md)|문자열의 서수 비교를 수행하는 방법을 보여 줍니다.|  
|[방법: String.Split를 사용하여 문자열 구문 분석 ](../../../csharp/programming-guide/strings/how-to-parse-strings-using-string-split.md)|`String.Split` 메서드를 사용하여 문자열을 구문 분석하는 방법을 보여 주는 코드 예제를 제공합니다.|  
|[방법: 문자열 처리 메서드를 사용하여 문자열 검색](../../../csharp/programming-guide/strings/how-to-search-strings-using-string-methods.md)|특정 메서드를 사용하여 문자열을 검색하는 방법에 대해 설명합니다.|  
|[방법: 정규식을 사용하여 문자열 검색](../../../csharp/programming-guide/strings/how-to-search-strings-using-regular-expressions.md)|정규식을 사용하여 문자열을 검색하는 방법을 설명합니다.|  
|[방법: 문자열이 숫자 값을 나타내는지 확인](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)|문자열을 안전하게 구문 분석하여 유효한 숫자 값을 가지고 있는지 확인하는 방법을 보여 줍니다.|  
|[방법: 문자열을 DateTime으로 변환](../../../csharp/programming-guide/strings/how-to-convert-a-string-to-a-datetime.md)|"01\/24\/2008"과 같은 문자열을 <xref:System.DateTime?displayProperty=fullName> 개체로 변환하는 방법을 보여 줍니다.|  
|[기본적인 문자열 작업](../Topic/Basic%20String%20Operations%20in%20the%20.NET%20Framework.md)|<xref:System.String?displayProperty=fullName> 및 <xref:System.Text.StringBuilder?displayProperty=fullName> 메서드를 사용하여 기본적인 문자열 작업을 수행하는 방법을 보여 주는 항목에 대한 링크를 제공합니다.|  
|[문자열 구문 분석](../Topic/Parsing%20Strings%20in%20the%20.NET%20Framework.md)|문자열에 문자 또는 공백을 삽입하는 방법에 대해 설명합니다.|  
|[문자열 비교](../Topic/Comparing%20Strings%20in%20the%20.NET%20Framework.md)|문자열을 비교하는 방법에 대한 정보가 포함되어 있고 C\#과 Visual Basic의 예제를 제공합니다.|  
|[StringBuilder 클래스 사용](../Topic/Using%20the%20StringBuilder%20Class%20in%20the%20.NET%20Framework.md)|<xref:System.Text.StringBuilder> 클래스를 사용하여 동적 문자열 개체를 만들고 수정하는 방법에 대해 설명합니다.|  
|[LINQ and Strings](../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)|LINQ 쿼리를 사용하여 다양한 문자열 작업을 수행하는 방법에 대한 정보를 제공합니다.|  
|[C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)|C\#의 프로그래밍 구문을 설명하는 항목에 대한 링크를 제공합니다.|  
  
## 중요 설명서 장  
 [변수에 대 한 자세한](란?LinkId%20=%20221230) 에서 [처음 Visual C\# 2010](란?LinkId%20=%20221214)