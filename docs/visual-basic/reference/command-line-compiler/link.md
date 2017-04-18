---
title: "/link (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e98c855f0a0185e9d1b6682df9fc734e9f1f07bc
ms.lasthandoff: 03/13/2017

---
# <a name="link-visual-basic"></a>/link(Visual Basic)
현재 컴파일 중인 프로젝트에 사용할 수 있는 지정된 된 어셈블리에서 COM 형식 정보를 확인 하는 컴파일러가 선택 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`fileList`|필수 요소. 어셈블리 파일 이름의 쉼표로 구분 된 목록입니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다.|  
  
## <a name="remarks"></a>설명  
 `/link` 옵션을 사용 하면 형식 정보를 포함 하는 응용 프로그램을 배포할 수 있습니다. 응용 프로그램 런타임 어셈블리에 대 한 참조를 요구 하지 않고 포함된 된 형식 정보를 구현 하는 런타임 어셈블리의 형식을 사용할 수 있습니다. 런타임 어셈블리의 여러 버전을 게시 하는 포함된 된 형식 정보를 포함 하는 응용 프로그램을 다시 컴파일하지 않고도 다양 한 버전 작업할 수 있습니다. 예를 들어 참조 [연습: 관리 되는 어셈블리의 형식 포함](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)합니다.  
  
 사용 하 여 `/link` 옵션은 COM interop를 사용 하 여 작업할 때 특히 유용 합니다. 응용 프로그램에 더 이상 주 interop 어셈블리를 PIA ()는 대상 컴퓨터에 필요한 수 있도록 COM 형식을 포함할 수 없습니다. `/link` 옵션 컴파일러가 결과 컴파일된 코드에 참조 된 interop 어셈블리에서 COM 형식 정보를 포함 하도록 합니다. COM 형식이 CLSID (GUID) 값으로 식별 됩니다. 결과적으로, 응용 프로그램가 같은 COM 형식이 같은 CLSID 값으로 설치 하는 대상 컴퓨터에서 실행할 수 있습니다. Microsoft Office를 자동화 하는 응용 프로그램은 좋은 예입니다. Office와 같은 응용 프로그램은 일반적으로 다양 한 버전에서 같은 CLSID 값 유지, 때문에 메서드, 속성 또는 이벤트가 참조 하는 COM 형식에 포함 된 응용 프로그램이 사용 하 고 대상 컴퓨터에.NET Framework 4 이상이 설치 되어 응용 프로그램 참조 된 COM 형식을 사용할 수 있습니다.  
  
 `/link` 옵션 인터페이스, 구조 및 대리자를 포함 합니다. COM 클래스를 포함 하는 것은 지원 되지 않습니다.  
  
> [!NOTE]
>  코드에 포함 된 COM 형식의 인스턴스를 만들 때 적절 한 인터페이스를 사용 하 여 인스턴스를 만들어야 합니다. CoClass를 사용 하 여 포함 된 COM 형식의 인스턴스를 만들려고 하면 오류가 발생 합니다.  
  
 설정 하는 `/link` 옵션 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], 어셈블리 참조를 추가 하 고 설정의 `Embed Interop Types` 속성을 **true**합니다. 기본값은 `Embed Interop Types` 속성은 **false**합니다.  
  
 COM 어셈블리 (어셈블리 A)에 연결 되는 경우 다른 COM 어셈블리 (어셈블리 B)를 참조 하는데, 다음 중 하나에 해당 하는 경우 어셈블리 B에 연결 해야 합니다.  
  
-   어셈블리 A에서에서 형식을 형식에서 상속 되거나 어셈블리 B의 인터페이스 구현  
  
-   필드, 속성, 이벤트 또는 어셈블리 B의 반환 형식이 나 매개 변수 형식의 변수가 있는 메서드가 호출 됩니다.  
  
 사용 하 여 [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) 어셈블리 참조 중 하나 이상이 있는 디렉터리를 지정할 수 있습니다.  
  
 마찬가지로 [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) 컴파일러 옵션은 `/link` 컴파일러 옵션 참조 자주 사용 되는 Vbc.rsp 지시 파일을 사용 하 여 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리. 사용 하 여 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) Vbc.rsp 파일을 사용 하도록 컴파일러에 원하지 않는 경우 컴파일러 옵션입니다.  
  
 약식 `/link` 는 `/l`합니다.  
  
## <a name="generics-and-embedded-types"></a>제네릭 및 포함 된 형식  
 다음 섹션에서는 interop 형식 포함 하는 응용 프로그램에서 제네릭 형식 사용에 제한 사항에 설명 합니다.  
  
### <a name="generic-interfaces"></a>제네릭 인터페이스  
 Interop 어셈블리를 포함 하는 제네릭 인터페이스를 사용할 수 없습니다. 다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-vb[VbLinkCompiler #&1;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]  
  
### <a name="types-that-have-generic-parameters"></a>제네릭 매개 변수가 있는 형식  
 Interop 어셈블리에서 해당 형식이 포함 된 제네릭 매개 변수를 가진 형식에 사용할 수 없습니다 경우 외부 어셈블리의 형식입니다. 인터페이스에는이 제한이 적용 되지 않습니다. 예를 들어는 <xref:Microsoft.Office.Interop.Excel.Range>에 정의 된 인터페이스는 <xref:Microsoft.Office.Interop.Excel>어셈블리.</xref:Microsoft.Office.Interop.Excel> </xref:Microsoft.Office.Interop.Excel.Range> 라이브러리의 interop 형식을 포함 하는 경우는 <xref:Microsoft.Office.Interop.Excel>어셈블리 및 형식을 갖는 매개 변수가 있는 제네릭 형식을 반환 하는 메서드는 노출 된 <xref:Microsoft.Office.Interop.Excel.Range>인터페이스 메서드에 다음 코드 예제와 같이 제네릭 인터페이스를 반환 해야 함을.</xref:Microsoft.Office.Interop.Excel.Range> </xref:Microsoft.Office.Interop.Excel>  
  
 [!code-vb[VbLinkCompiler #&2;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]  
[!code-vb[VbLinkCompiler #&3;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]  
[!code-vb[VbLinkCompiler #&4;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]  
  
 다음 예제에서는 클라이언트 코드를 반환 하는 메서드를 호출할 수는 <xref:System.Collections.IList>오류 없이 제네릭 인터페이스.</xref:System.Collections.IList>  
  
 [!code-vb[VbLinkCompiler #&5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]  
  
## <a name="example"></a>예제  
 다음 코드는 소스 파일을 컴파일하 `OfficeApp.vb` 의 어셈블리를 참조 하 고 `COMData1.dll` 및 `COMData2.dll` 생성 `OfficeApp.exe`합니다.  
  
```vb  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [연습: 관리 되는 어셈블리의 형식 포함](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)   
 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [COM Interop 소개](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
