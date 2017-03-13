---
title: "Troubleshooting Interoperability (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interop, deploying assemblies"
  - "assemblies [Visual Basic]"
  - "interop, installing assemblies that share components"
  - "COM objects, troubleshooting"
  - "interop, sharing components"
  - "troubleshooting interoperability"
  - "interoperability, troubleshooting"
  - "COM interop, troubleshooting"
  - "assemblies [Visual Basic], deploying"
  - "troubleshooting Visual Basic, interoperability"
  - "interop assemblies"
  - "interoperability, sharing components"
  - "shared components, using with assemblies"
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Troubleshooting Interoperability (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

COM과 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]의 관리 코드를 상호 운용할 때 다음과 같은 일반적인 문제가 발생할 수 있습니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a> Interop 마샬링  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]에 속하지 않는 데이터 형식을 사용해야 할 수도 있습니다.  Interop 어셈블리가 COM 개체에 대한 대부분의 작업을 처리하지만 관리되는 개체가 COM에 노출되는 경우에는 사용자가 데이터 형식을 제어해야 할 수도 있습니다.  예를 들어, 클래스 라이브러리의 구조체는 Visual Basic 6.0 이전 버전에서 만든 COM 개체로 보낸 문자열에 관리되지 않는 형식의 `BStr`을 지정해야 합니다.  이러한 경우 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 관리되는 형식을 관리되지 않는 형식으로 노출시킬 수 있습니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a> 비관리 코드로 고정 길이 문자열 내보내기  
 Visual Basic 6.0 이전 버전에서 문자열은 Null 종결 문자 없이 일련의 바이트로서 COM 개체로 내보내집니다.  다른 언어와 호환될 수 있도록 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]에서는 문자열을 내보낼 때 종결 문자를 포함합니다.  이러한 호환성 문제를 해결하는 가장 좋은 방법은 종결 문자가 없는 문자열을 `Byte` 또는 `Char` 배열로 내보내는 것입니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a> 상속 계층 구조 내보내기  
 관리되는 클래스 계층 구조는 COM 개체로 노출될 때 결합됩니다.  예를 들어, 멤버가 있는 기본 클래스를 정의한 다음 COM 개체로 노출되는 파생 클래스에서 기본 클래스를 상속하는 경우, COM 개체의 파생 클래스를 사용하는 클라이언트가 상속된 멤버를 사용할 수 없습니다.  기본 클래스 멤버는 COM 개체로부터 기본 클래스의 인스턴스로서만 액세스할 수 있습니다. 또한 이 경우 기본 클래스는 COM 개체로 만들어져야 합니다.  
  
## 오버로드된 메서드  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 오버로드된 메서드를 만들 수 있지만, COM에서는 이러한 메서드가 지원되지 않습니다.  오버로드된 메서드가 들어 있는 클래스를 COM 개체로 노출하면 오버로드된 메서드에 사용할 새 메서드 이름이 생성됩니다.  
  
 예를 들어 `Synch` 메서드에 대한 두 개의 오버로드가 있는 클래스를 가정해 봅니다.  이 클래스를 COM 개체로 노출하면 `Synch` 및 `Synch_2`라는 메서드 이름이 새로 생성됩니다.  
  
 이름이 변경됨으로 인해 COM 개체 소비자에게 두 가지 문제가 발생할 수 있습니다.  
  
1.  생성된 메서드 이름을 클라이언트에서 예측할 수 없습니다.  
  
2.  COM 개체로 노출된 클래스나 해당 기본 클래스에 새 오버로드가 추가되면 이러한 클래스에서 생성된 메서드 이름이 변경되어  버전 관리 문제가 발생할 수 있습니다.  
  
 두 가지 문제를 해결하려면 COM 개체로 노출되는 개체를 개발할 때 오버로드를 사용하는 대신 각 메서드에 고유한 이름을 부여합니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a> Interop 어셈블리를 통해 COM 개체 사용  
 해당 COM 개체를 대체하는 관리 코드인 것처럼 interop 어셈블리를 사용할 수 있습니다.  그러나 이 어셈블리는 래퍼이며 실제 COM 개체는 아니므로 interop 어셈블리와 표준 어셈블리는 사용 방법에 있어 약간의 차이가 있습니다.  예를 들면 클래스의 노출이나 매개 변수 및 반환 값의 데이터 형식에서 차이점을 보입니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a> 인터페이스와 클래스 모두로 노출되는 클래스  
 표준 어셈블리의 클래스와는 달리 COM 클래스는 COM 클래스를 나타내는 인터페이스와 클래스 두 가지 모두로 interop 어셈블리에 노출됩니다.  인터페이스의 이름은 해당 COM 클래스의 이름과 동일합니다.  interop 클래스의 이름은 원래 COM 클래스의 이름과 같지만 "Class"란 단어가 추가됩니다.  예를 들어, COM 개체의 interop 어셈블리에 대한 참조를 갖는 프로젝트가 있다고 가정합시다.  COM 클래스의 이름이 `MyComClass`이고 IntelliSense 및 개체 브라우저에는 `MyComClass`라는 인터페이스와 `MyComClassClass`라는 클래스가 표시됩니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a> .NET Framework 클래스의 인스턴스 만들기  
 일반적으로 클래스 이름을 지정한 `New` 문을 사용하여 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 클래스의 인스턴스를 만듭니다.  COM 클래스를 interop 어셈블리로 표시하는 것이 `New` 문을 인터페이스와 함께 사용할 수 있는 유일한 경우입니다.  `Inherits` 문과 함께 COM 클래스를 사용하는 경우를 제외하고는 클래스와 같은 방법으로 인터페이스를 사용할 수 있습니다.  다음 코드에서는 Microsoft ActiveX Data Objects 2.8 라이브러리 COM 개체에 대한 참조가 포함된 프로젝트에서 `Command` 개체를 만드는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrInterop#20](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 그러나 COM 클래스를 파생 클래스에 대한 기본으로 사용하는 경우에는 다음 코드와 같이 COM 클래스를 나타내는 interop 클래스를 사용해야 합니다.  
  
 [!code-vb[VbVbalrInterop#21](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Interop 어셈블리는 COM 클래스를 나타내는 인터페이스를 암시적으로 구현합니다.  이러한 인터페이스를 `Implements` 문으로 구현하려고 하면 오류가 발생합니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a> 매개 변수 및 반환 값의 데이터 형식  
 표준 어셈블리 멤버와 달리 interop 어셈블리 멤버는 개체의 원래 선언에 사용된 것과 다른 데이터 형식을 사용할 수 있습니다.  Interop 어셈블리가 암시적으로 COM 형식을 호환되는 공용 언어 런타임 형식으로 변환하더라도 런타임 오류가 발생하지 않도록 양쪽에서 사용되는 데이터 형식에 주의를 기울여야 합니다.  예들 들어, Visual Basic 6.0 이전 버전으로 만든 COM 개체에서 `Integer` 형식의 값은 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]의 해당 형식인 `Short`로 간주됩니다.  가져온 멤버를 사용하기 전에 개체 브라우저를 사용하여 해당 멤버의 특성을 검토하는 것이 좋습니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a> 모듈 수준 COM 메서드  
 대부분의 COM 개체는 `New` 키워드를 사용하여 COM 클래스의 인스턴스를 만든 다음 해당 개체의 메서드를 호출하는 방법으로 사용합니다.  그러나 `AppObj` 또는 `GlobalMultiUse` COM 클래스가 포함된 COM 개체의 경우에는 이 규칙이 적용되지 않습니다.  이러한 클래스는 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] 클래스의 모듈 수준 메서드와 유사합니다.  Visual Basic 6.0과 그 이전 버전에서는 사용자가 처음으로 이러한 개체의 메서드 중 하나를 호출할 때 개체의 인스턴스가 암시적으로 만들어집니다.  예를 들어, Visual Basic 6.0에서 Microsoft DAO 3.6 개체 라이브러리에 대한 참조를 추가한 후에는 인스턴스를 먼저 만들지 않고도 `DBEngine` 메서드를 호출할 수 있습니다.  
  
```  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]에서는 COM 개체의 메서드를 사용하기 전에 먼저 COM 개체의 인스턴스를 만들어야 합니다.  [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]에서 이러한 메서드를 사용하려면 원하는 클래스의 변수를 선언한 다음 new 키워드를 사용하여 개체 변수에 개체를 할당합니다.  해당 클래스의 인스턴스를 하나만 만들려는 경우에는 `Shared` 키워드를 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrInterop#23](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a> 이벤트 처리기에서 처리되지 않은 오류  
 일반적인 상호 운용성 문제에는 COM 개체에 의해 발생된 이벤트를 처리하는 이벤트 처리기의 오류가 포함됩니다.  특별히 `On Error` 또는 `Try...Catch...Finally` 문을 사용하여 오류를 검사하지 않으면 이러한 오류는 무시됩니다.  예를 들어, 다음은 Microsoft ActiveX Data Objects 2.8 라이브러리 COM 개체에 대한 참조가 포함된 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] 프로젝트에서 가져온 예입니다.  
  
 [!code-vb[VbVbalrInterop#24](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 이 예제에서는 예상한 대로 오류가 발생합니다.  그러나 같은 예제를 `Try...Catch...Finally` 블록 없이 사용하면 `OnError Resume Next` 문을 사용한 것처럼 오류가 무시됩니다.  오류를 처리하지 않을 경우 0으로 나누기는 아무런 경고 없이 실패합니다.  왜냐하면 이러한 오류는 처리되지 않은 예외 오류를 발생시키지 않기 때문입니다. 따라서 COM 개체의 이벤트를 처리하는 이벤트 처리기에서는 어떤 형태로든 예외를 처리해 주어야 합니다.  
  
### COM interop 오류 이해  
 오류 처리를 사용하지 않을 경우 interop 호출은 종종 정보가 거의 제공되지 않는 오류를 생성합니다.  되도록이면 문제가 발생할 경우 보다 많은 정보를 제공할 수 있도록 구조적 오류 처리를 사용하는 것이 좋습니다.  이는 응용 프로그램을 디버깅할 때 특히 유용할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-vb[VbVbalrInterop#25](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 예외 개체의 내용을 검사하여 오류 설명, HRESULT 및 COM 오류의 소스 등의 정보를 찾을 수 있습니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a> ActiveX 컨트롤 문제  
 Visual Basic 6.0에서 작동하는 대부분의 ActiveX 컨트롤은 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]에서도 올바르게 작동합니다.  그러나 컨테이너 컨트롤이나 시각적으로 다른 컨트롤을 포함하는 컨트롤은 예외입니다.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]에서 올바르게 작동하지 않는 이전 버전 컨트롤의 예는 다음과 같습니다.  
  
-   Microsoft Forms 2.0 Frame 컨트롤  
  
-   Up\-Down 컨트롤\(spin 컨트롤이라고도 함\)  
  
-   Sheridan Tab 컨트롤  
  
 지원되지 않는 ActiveX 컨트롤 문제를 해결할 수 있는 방법은 몇 가지에 불과합니다.  원본 소스 코드가 있는 경우에는 기존 컨트롤을 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]로 마이그레이션할 수 있습니다.  또는 소프트웨어 공급업체에 문의하여 업데이트된 .NET 호환 버전의 컨트롤을 받은 다음 지원되지 않는 ActiveX 컨트롤 대신 사용할 수 있습니다.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a> 컨트롤의 읽기 전용 속성을 참조로 전달  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]에서는 가끔 일부 이전 버전 ActiveX 컨트롤의 `ReadOnly` 속성을 다른 프로시저에 `ByRef` 매개 변수로 전달할 때 "오류 0x800A017F CTL\_E\_SETNOTSUPPORTED"와 같은 COM 오류가 발생합니다.  Visual Basic 6.0에서는 이와 비슷한 프로시저를 호출하여도 오류를 발생시키지 않으며 매개 변수는 값으로 전달된 것처럼 처리됩니다.  [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]에 표시되는 오류 메시지는 속성 `Set` 프로시저가 없는 속성을 변경하려고 했음을 보고하는 COM 개체입니다.  
  
 호출되는 프로시저에 대한 액세스 권한이 있으면 `ReadOnly` 속성을 받아들이는 매개 변수를 선언할 때 `ByVal` 키워드를 사용하여 이 오류를 방지할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-vb[VbVbalrInterop#26](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 호출되는 프로시저의 소스 코드에 대한 액세스 권한이 없으면 호출하는 프로시저 주위에 대괄호를 추가하여 속성이 값으로 전달되도록 할 수 있습니다.  예를 들어, Microsoft ActiveX Data Objects 2.8 라이브러리 COM 개체에 대한 참조가 포함된 프로젝트에서 다음을 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrInterop#27](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a> Interop을 노출하는 어셈블리 배포  
 COM 인터페이스를 노출하는 어셈블리를 배포하는 데는 몇 가지 주의할 점이 있습니다.  예를 들어, 서로 다른 응용 프로그램에서 같은 COM 어셈블리를 참조하는 경우 문제가 발생할 수 있습니다.  이러한 상황은 새 버전의 어셈블리를 설치했는데 다른 응용 프로그램에서 이전 버전의 어셈블리를 계속 사용하고 있는 경우 흔히 발생합니다.  DLL을 공유하는 어셈블리를 제거하면 다른 어셈블리에서 해당 DLL을 사용하지 못할 수도 있습니다.  
  
 이러한 문제를 방지하려면 공유 어셈블리를 GAC\(전역 어셈블리 캐시\)에 설치하고 구성 요소에 대해 MergeModule을 사용해야 합니다.  응용 프로그램을 GAC에 설치할 수 없으면 버전별 하위 디렉터리 아래의 CommonFilesFolder에 설치해야 합니다.  
  
 공유되지 않는 어셈블리는 호출 응용 프로그램과 함께 같은 디렉터리에 배치해야 합니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe\(형식 라이브러리 내보내기\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [전역 어셈블리 캐시](../Topic/Global%20Assembly%20Cache.md)