---
title: "/vbruntime | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
dev_langs:
- VB
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
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
ms.openlocfilehash: 455f950988b540b74874ce38882c59059f77ea8f
ms.lasthandoff: 03/13/2017

---
# <a name="vbruntime"></a>/vbruntime
컴파일러에서 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하거나 특정 런타임 라이브러리를 참조하여 컴파일하도록 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>인수  
 \-  
 Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하십시오.  
  
 \+  
 기본 Visual Basic 런타임 라이브러리에 대 한 참조를 사용 하 여 컴파일하십시오.  
  
 \*  
 Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하고 어셈블리를 Visual Basic 런타임 라이브러리에서 핵심 기능을 포함 합니다.  
  
 `path`  
 지정된 된 라이브러리 (DLL)에 대 한 참조를 사용 하 여 컴파일하십시오.  
  
## <a name="remarks"></a>주의  
 `/vbruntime` 컴파일러 옵션을 사용 하면 컴파일러는 Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하도록를 지정할 수 있습니다. Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하는 경우 Visual Basic 런타임 도우미에 대 한 호출을 생성 하는 코드 또는 언어 구문에 대해 오류 또는 경고가 기록 됩니다. (A *Visual Basic 런타임 도우미* 특정 언어 의미 체계를 실행 하는 런타임 시 호출 되는 Microsoft.VisualBasic.dll에 정의 된 함수입니다.)  
  
 `/vbruntime+` 되지 않았을 때 발생 하는 동일한 동작을 생성 하는 옵션 `/vbruntime` 스위치를 지정 합니다. 사용할 수는 `/vbruntime+` 이전 재정의 하는 옵션 `/vbruntime` 스위치입니다.  
  
 대부분의 개체는 `My` 형식을 사용할 수 없는 사용 하는 경우는 `/vbruntime-` 또는 `vbruntime:``path` 옵션입니다.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Visual Basic 런타임 핵심 기능을 포함합니다.  
 `/vbruntime*` 옵션을 사용 하면 런타임 라이브러리에 대 한 참조 없이 컴파일할 수 있습니다. 대신, Visual Basic 런타임 라이브러리의 핵심 기능을 사용자 어셈블리에 포함 됩니다. 응용 프로그램이 Visual Basic 런타임 포함 하지 않는 플랫폼에서 실행 하는 경우이 옵션을 사용할 수 있습니다.  
  
 다음 런타임 멤버가 포함 됩니다.  
  
-   <xref:Microsoft.VisualBasic.CompilerServices.Conversions>클래스</xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>메서드</xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>메서드</xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>메서드</xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack>상수</xref:Microsoft.VisualBasic.Constants.vbBack>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr>상수</xref:Microsoft.VisualBasic.Constants.vbCr>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf>상수</xref:Microsoft.VisualBasic.Constants.vbCrLf>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed>상수</xref:Microsoft.VisualBasic.Constants.vbFormFeed>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf>상수</xref:Microsoft.VisualBasic.Constants.vbLf>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine>상수</xref:Microsoft.VisualBasic.Constants.vbNewLine>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar>상수</xref:Microsoft.VisualBasic.Constants.vbNullChar>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString>상수</xref:Microsoft.VisualBasic.Constants.vbNullString>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab>상수</xref:Microsoft.VisualBasic.Constants.vbTab>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>상수</xref:Microsoft.VisualBasic.Constants.vbVerticalTab>  
  
-   일부 개체는 `My` 형식  
  
 사용 하 여 컴파일하는 경우는 `/vbruntime*` 옵션 및 코드의 핵심 기능이 포함 되지 않은 Visual Basic 런타임 라이브러리에서 멤버 참조, 컴파일러는 멤버를 사용할 수 없다는 나타내는 오류를 반환 합니다.  
  
## <a name="referencing-a-specified-library"></a>지정된 된 라이브러리를 참조합니다.  
 사용할 수는 `path` 인수를 기본 Visual Basic 런타임 라이브러리 대신 사용자 지정 런타임 라이브러리에 대 한 참조를 사용 하 여 컴파일합니다.  
  
 경우에 대 한 값은 `path` 인수는 DLL에는 정규화 된 경로, 컴파일러는 런타임 라이브러리와 해당 파일을 사용 합니다. 경우에 대 한 값은 `path` 인수를 DLL로 정규화 된 경로가 아닙니다, Visual Basic 컴파일러가 현재 폴더에서 식별 된 DLL에 대 한 가장 먼저 검색 합니다. 사용 하 여 지정 된 경로에서 검색 한 다음는 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) 컴파일러 옵션입니다. 하는 경우는 `/sdkpath` 컴파일러 옵션이 사용 되지 않으면, 컴파일러는.NET Framework 폴더에 식별 된 DLL에 대 한 검색 (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>예제  
 다음 예제를 사용 하는 방법을 보여 줍니다는 `/vbruntime` 옵션을 사용자 지정 라이브러리에 대 한 참조를 사용 하 여 컴파일합니다.  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 코어 – Visual Studio 2010 s p 1의 새로운 컴파일 모드](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)   
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
