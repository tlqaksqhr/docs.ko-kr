---
title: "공통 특성 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f470e6ff3e316076d71a34346f741cc4504471a3
ms.lasthandoff: 03/13/2017

---
# <a name="common-attributes-visual-basic"></a>공통 특성 (Visual Basic)
이 항목에서는 Visual Basic 프로그램에서 가장 일반적으로 사용 되는 특성을 설명 합니다.  
  
-   [전역 특성](#Global)  
  
-   [사용 되지 않는 특성](#Obsolete)  
  
-   [조건부 특성](#Conditional)  
  
-   [호출자 정보 특성](#CallerInfo)  
  
-   [Visual Basic 특성](#VB)  
  
##  <a name="Global"></a>전역 특성  
 대부분의 특성은 클래스 또는 메서드;와 같은 특정 언어 요소에 적용 됩니다. 그러나 일부 특성은 전역-전체 어셈블리 또는 모듈에 적용 합니다. 예를 들어는 <xref:System.Reflection.AssemblyVersionAttribute>를 다음과 같이 어셈블리에 버전 정보를 포함 시킬 특성을 사용할 수 있습니다:</xref:System.Reflection.AssemblyVersionAttribute>  
  
```vb  
<Assembly: AssemblyVersion("1.0.0.0")>  
```  
  
 전역 특성 후 소스 코드에 표시 합니다. 최상위`Imports` 문 및 유형, 모듈 또는 네임 스페이스 선언 앞입니다. 전역 특성은 여러 소스 파일에 나타날 수 있지만 단일 컴파일 단계에서 파일을 컴파일해야 합니다. Visual Basic 프로젝트에 대 한 전역 특성 (파일이 만들어집니다 자동으로 Visual Studio에서 프로젝트를 만들 때) AssemblyInfo.vb 파일에 일반적으로 배치 됩니다.  
  
 어셈블리 특성은 어셈블리에 대한 정보를 제공하는 값입니다. 다음과 같은 범주로 분류 됩니다.  
  
-   어셈블리 id 특성  
  
-   정보 특성  
  
-   어셈블리 매니페스트 특성  
  
### <a name="assembly-identity-attributes"></a>어셈블리 ID 특성  
 어셈블리의 id를 확인 하는 세 가지 특성 (강력한 이름으로, 해당 하는 경우): 이름, 버전 및 culture입니다. 이러한 특성은 어셈블리의 전체 이름을 구성 및 코드에서 참조 하는 경우에 필요 합니다. 어셈블리의 버전 및 특성을 사용 하 여 문화권을 설정할 수 있습니다. 그러나 이름 값은 Visual Studio IDE에서 컴파일러에 의해 설정 됩니다는 [어셈블리 정보 대화 상자](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), 어셈블리 매니페스트가 포함 된 파일을 기반으로 하는 어셈블리 링커 (Al.exe)는 어셈블리를 만들 때 또는 합니다. <xref:System.Reflection.AssemblyFlagsAttribute>특성은 어셈블리의 여러 복사본을 함께 사용할 수 있는지 여부를 지정 합니다.</xref:System.Reflection.AssemblyFlagsAttribute>  
  
 다음 표에서 id 특성을 보여 줍니다.  
  
|특성|용도|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName>|어셈블리의 id를 자세히 설명 합니다.|  
|<xref:System.Reflection.AssemblyVersionAttribute></xref:System.Reflection.AssemblyVersionAttribute>|어셈블리의 버전을 지정 합니다.|  
|<xref:System.Reflection.AssemblyCultureAttribute></xref:System.Reflection.AssemblyCultureAttribute>|어셈블리에서 지원하는 문화권을 지정합니다.|  
|<xref:System.Reflection.AssemblyFlagsAttribute></xref:System.Reflection.AssemblyFlagsAttribute>|동일한 컴퓨터, 동일한 프로세스에서 또는 동일한 응용 프로그램 도메인에서 어셈블리-병렬 실행을 지원 하는지 여부를 지정 합니다.|  
  
### <a name="informational-attributes"></a>정보 특성  
 정보 특성을 사용하여 어셈블리에 대한 추가 회사 또는 제품 정보를 제공할 수 있습니다. 다음 표에서에 정의 된 추가 특성은 <xref:System.Reflection?displayProperty=fullName>네임 스페이스.</xref:System.Reflection?displayProperty=fullName>  
  
|특성|용도|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute></xref:System.Reflection.AssemblyProductAttribute>|어셈블리 매니페스트에 대 한 제품 이름을 지정 하는 사용자 지정 특성을 정의 합니다.|  
|<xref:System.Reflection.AssemblyTrademarkAttribute></xref:System.Reflection.AssemblyTrademarkAttribute>|어셈블리 매니페스트에 대 상표를 지정 하는 사용자 지정 특성을 정의 합니다.|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute></xref:System.Reflection.AssemblyInformationalVersionAttribute>|어셈블리 매니페스트에 대 한 정보 버전을 지정 하는 사용자 지정 특성을 정의 합니다.|  
|<xref:System.Reflection.AssemblyCompanyAttribute></xref:System.Reflection.AssemblyCompanyAttribute>|어셈블리 매니페스트에 대 한 회사 이름을 지정 하는 사용자 지정 특성을 정의 합니다.|  
|<xref:System.Reflection.AssemblyCopyrightAttribute></xref:System.Reflection.AssemblyCopyrightAttribute>|어셈블리 매니페스트에 대 한 저작권 정보를 지정 하는 사용자 지정 특성을 정의 합니다.|  
|<xref:System.Reflection.AssemblyFileVersionAttribute></xref:System.Reflection.AssemblyFileVersionAttribute>|Win32 파일 버전 리소스에 대 한 특정 버전 번호를 사용 하도록 컴파일러에 지시 합니다.|  
|<xref:System.CLSCompliantAttribute></xref:System.CLSCompliantAttribute>|어셈블리의 공용 언어 사양 (CLS 규격) 여부를 나타냅니다.|  
  
### <a name="assembly-manifest-attributes"></a>어셈블리 매니페스트 특성  
 어셈블리 매니페스트에 있는 정보를 제공 하도록 어셈블리 매니페스트 특성을 사용할 수 있습니다. 여기에 제목, 설명, 기본 별칭 및 구성이 포함 됩니다. 다음 표에서 어셈블리 매니페스트 특성에 정의 된 <xref:System.Reflection?displayProperty=fullName>네임 스페이스.</xref:System.Reflection?displayProperty=fullName>  
  
|특성|용도|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute></xref:System.Reflection.AssemblyTitleAttribute>|어셈블리 매니페스트에 대 한 어셈블리 제목을 지정 하는 사용자 지정 특성을 정의 합니다.|  
|<xref:System.Reflection.AssemblyDescriptionAttribute></xref:System.Reflection.AssemblyDescriptionAttribute>|어셈블리 매니페스트에 대 한 어셈블리 설명을 지정 하는 사용자 지정 특성을 정의 합니다.|  
|<xref:System.Reflection.AssemblyConfigurationAttribute></xref:System.Reflection.AssemblyConfigurationAttribute>|어셈블리 매니페스트에 대 한 어셈블리 구성 (예: 정식 또는 디버그)를 지정 하는 사용자 지정 특성을 정의 합니다.|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute></xref:System.Reflection.AssemblyDefaultAliasAttribute>|어셈블리 매니페스트에 대 한 기본 별칭을 정의합니다.|  
  
##  <a name="Obsolete"></a>사용 되지 않는 특성  
 `Obsolete` 특성은 프로그램 엔터티는 더 이상 사용 하 여 좋은 것으로 표시 합니다. 각각의 것으로 표시 하는 엔터티 사용 경고 또는 오류가 특성 구성 된 방식에 따라 생성 됩니다. 예:  
  
```vb  
<System.Obsolete("use class B")>   
Class A  
    Sub Method()  
    End Sub  
End Class  
  
Class B  
    <System.Obsolete("use NewMethod", True)>   
    Sub OldMethod()  
    End Sub  
  
    Sub NewMethod()  
    End Sub  
End Class  
```  
  
 이 예제는 `Obsolete` 특성은 클래스에 적용 `A` 및 메서드에 `B.OldMethod`합니다. 특성 생성자의 두 번째 인수에 적용 되므로 `B.OldMethod` 로 설정 된 `true`,이 메서드는 컴파일러 오류는 발생 클래스를 사용 하 여 반면 `A` 경고가 생성 됩니다. 그러나 호출 `B.NewMethod`, 없는 경고 또는 오류를 생성 합니다.  
  
 특성 생성자의 첫 번째 인수로 제공 하는 문자열 경고 또는 오류의 일부로 표시 됩니다. 예를 들어 이전 정의 사용 하면 다음 코드는 두 개의 경고와 하나 이상의 오류가 생성 됩니다.  
  
```vb  
' Generates 2 warnings:  
' Dim a As New A  
' Generate no errors or warnings:  
  
Dim b As New B  
b.NewMethod()  
  
' Generates an error, terminating compilation:  
' b.OldMethod()  
```  
  
 클래스에 대 한 두 가지 경고가 `A` 생성: 클래스 생성자에 대 한 여러 개 있는 클래스 참조의 선언에 대 한 한 합니다.  
  
 `Obsolete` 특성 인수 없이 사용할 수 있지만 때문에 대 한 설명을 포함 하 여 항목 사용 되지 않으며 대신 사용 하는 것이 좋습니다.  
  
 `Obsolete` 특성은&1; 회용 특성 및 특성을 허용 하는 모든 엔터티에 적용할 수 있습니다. `Obsolete`<xref:System.ObsoleteAttribute>.</xref:System.ObsoleteAttribute> 별칭은  
  
##  <a name="Conditional"></a>조건부 특성  
 `Conditional` 이 특성은 메서드의 실행을 전처리 식별자에 따라 다릅니다. `Conditional` 특성에 대 한 별칭은 <xref:System.Diagnostics.ConditionalAttribute>, 메서드 또는 특성 클래스에 적용할 수 및</xref:System.Diagnostics.ConditionalAttribute>  
  
 이 예제에서는 `Conditional` 프로그램 관련 진단 정보의 표시를 사용할지 여부를 메서드에 적용 됩니다.  
  
```vb  
#Const TRACE_ON = True  
Imports System  
Imports System.Diagnostics  
Module TestConditionalAttribute  
    Public Class Trace  
        <Conditional("TRACE_ON")>   
        Public Shared Sub Msg(ByVal msg As String)  
            Console.WriteLine(msg)  
        End Sub  
  
    End Class  
  
    Sub Main()  
        Trace.Msg("Now in Main...")  
        Console.WriteLine("Done.")  
    End Sub  
End Module  
```  
  
 하는 경우는 `TRACE_ON` 식별자가 정의 추적 출력이 표시 됩니다.  
  
 `Conditional` 특성은 자주 사용 된 `DEBUG` 다음과 같은 추적 및 디버그를 작성 하지만 속하지 않은 릴리스 빌드에 대 한 로깅 기능을 사용 하도록 설정 하는 식별자:  
  
```vb  
<Conditional("DEBUG")>   
Shared Sub DebugMethod()  
  
End Sub  
```  
  
 조건부로 표시 된 메서드를 호출 하는 경우 지정된 된 전처리 기호 유무 호출 생략 포함 여부 결정 합니다. 기호가 정의 된 경우는 호출이 포함; 됩니다. 그렇지 않으면 호출을 생략 합니다. 사용 하 여 `Conditional` 깔끔하고 더 세련 되 고 오류 발생 우려가 적은 내부 메서드를 포함 하는 대체 항목 `#if…#endif` 블록을 다음과 같이 합니다.  
  
```vb  
#If DEBUG Then  
    Sub ConditionalMethod()  
    End Sub  
#End If  
```  
  
 조건부 메서드는 클래스 또는 구조체 선언의 하며 반환 값이 없어야 합니다.  
  
### <a name="using-multiple-identifiers"></a>여러 식별자를 사용 하 여  
 메서드에 있는 경우 여러 `Conditional` 특성을 조건부 기호 중 하나 이상 정의 되어 있으면 메서드에 대 한 호출이 포함 됩니다 (즉, 기호 논리적으로 연결 되는 OR 연산자를 사용 하 여). 이 예제에서는 하나 있는지 `A` 또는 `B` 메서드 호출에서 발생 합니다.  
  
```vb  
<Conditional("A"), Conditional("B")>   
Shared Sub DoIfAorB()  
  
End Sub  
```  
  
 논리적 AND 연산자를 사용 하 여 기호를 연결 하는 효과 얻으려면 순차적인 조건부 메서드를 정의할 수 있습니다. 두 경우에 아래의 두 번째 메서드는 실행 하는 예를 들어 `A` 및 `B` 정의 됩니다.  
  
```vb  
<Conditional("A")>   
Shared Sub DoIfA()  
    DoIfAandB()  
End Sub  
  
<Conditional("B")>   
Shared Sub DoIfAandB()  
    ' Code to execute when both A and B are defined...  
End Sub  
```  
  
### <a name="using-conditional-with-attribute-classes"></a>조건부를 사용 하 여 특성 클래스  
 `Conditional` 특성은 특성 클래스 정의에 적용할 수도 있습니다. 이 예제에서는 사용자 지정 특성 `Documentation` 디버그 정의 된 경우 메타 데이터 정보를 추가 합니다.  
  
```vb  
<Conditional("DEBUG")>   
Public Class Documentation  
    Inherits System.Attribute  
    Private text As String  
    Sub New(ByVal doc_text As String)  
        text = doc_text  
    End Sub  
End Class  
  
Class SampleClass  
    ' This attribute will only be included if DEBUG is defined.  
    <Documentation("This method displays an integer.")>   
    Shared Sub DoWork(ByVal i As Integer)  
        System.Console.WriteLine(i)  
    End Sub  
End Class  
```  
  
##  <a name="CallerInfo"></a>호출자 정보 특성  
 호출자 정보 특성을 사용하여 메서드 호출자에 대한 정보를 얻을 수 있습니다. 소스 코드의 파일 경로, 소스 코드와 호출자의 멤버 이름에 줄 번호를 가져올 수 있습니다.  
  
 멤버 호출자 정보를 사용 하 여 선택적 매개 변수에 적용 되는 특성입니다. 각 선택적 매개 변수 기본값을 지정 합니다. 에 정의 된 호출자 정보 특성을 나열 하는 다음 표에 <xref:System.Runtime.CompilerServices?displayProperty=fullName>네임 스페이스:</xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
|특성|설명|형식|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|호출자를 포함한 소스 파일의 전체 경로입니다. 컴파일 타임에는 경로입니다.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|메서드는 소스 파일의 줄 번호입니다.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|메서드 이름 또는 호출자의 속성 이름입니다. 자세한 내용은 참조 [호출자 정보 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md)합니다.|`String`|  
  
 호출자 정보 특성에 대 한 자세한 내용은 참조 [호출자 정보 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md)합니다.  
  
##  <a name="VB"></a>Visual Basic 특성  
 다음 표에서 Visual Basic에 관련 된 특성을 나열 합니다.  
  
|특성|용도|  
|---------------|-------------|  
|<xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute>|컴파일러에 알리는 클래스를 COM 개체로 노출 되어야 합니다.|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute></xref:Microsoft.VisualBasic.HideModuleNameAttribute>|모듈 멤버를에 모듈에 필요한 정규화를 사용 하 여 액세스할 수 있습니다.|  
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute></xref:Microsoft.VisualBasic.VBFixedStringAttribute>|파일 입력 및 출력으로 사용 하기 위해 구조에는 고정 길이 문자열의 크기를 지정 함수입니다.|  
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute></xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|파일 입력 및 출력으로 사용 하기 위해 구조의 고정 배열의 크기를 지정 함수입니다.|  
  
### <a name="comclassattribute"></a>COMClassAttribute  
 사용 하 여 `COMClassAttribute` Visual Basic에서 COM 구성 요소를 만드는 과정을 간소화 하기 위해. COM 개체는.NET Framework 어셈블리에서 및 없이 상당히 다른 `COMClassAttribute`를 위해 다양 한 Visual Basic에서 COM 개체를 생성 하는 단계를 수행 해야 합니다. 로 표시 된 클래스 `COMClassAttribute`, 컴파일러 여러이 단계를 자동으로 수행 합니다.  
  
### <a name="hidemodulenameattribute"></a>HideModuleNameAttribute  
 사용 하 여 `HideModuleNameAttribute` 모듈 멤버에 필요한 모듈에 대 한 한정만을 사용 하 여 액세스할 수 있도록 합니다.  
  
### <a name="vbfixedstringattribute"></a>VBFixedStringAttribute  
 사용 하 여 `VBFixedStringAttribute` 고정 길이의 문자열을 만들려면 Visual Basic을 강제 합니다. 문자열에는 기본적으로 가변 길이 및이 특성은 문자열을 파일을 저장할 때 유용 합니다. 다음 코드에서는이 보여 줍니다.  
  
```vb  
Structure Worker  
    ' The runtime uses VBFixedString to determine   
    ' if the field should be written out as a fixed size.  
    <VBFixedString(10)> Public LastName As String  
    <VBFixedString(7)> Public Title As String  
    <VBFixedString(2)> Public Rank As String  
End Structure  
```  
  
### <a name="vbfixedarrayattribute"></a>VBFixedArrayAttribute  
 사용 하 여 `VBFixedArrayAttribute` 크기가 고정 된 배열을 선언할 수 있습니다. 배열은 Visual Basic 문자열 처럼 기본적으로 가변 길이입니다. 이 특성은 직렬화 또는 데이터 파일에 쓰는 경우에 유용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md)   
 [특성](https://msdn.microsoft.com/library/5x6cd29c)   
 [리플렉션 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [(Visual Basic) 리플렉션을 사용 하 여 특성 액세스](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
