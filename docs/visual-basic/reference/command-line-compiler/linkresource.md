---
title: "/linkresource (Visual Basic) | Microsoft 문서"
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
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fafde6563340189108a879b82e7e880aca690b39
ms.lasthandoff: 03/13/2017

---
# <a name="linkresource-visual-basic"></a>/linkresource(Visual Basic)
관리되는 리소스에 대한 링크를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>인수  
 `filename`  
 필수 요소. 어셈블리에 연결할 리소스 파일입니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").  
  
 `identifier`  
 선택적 요소. 리소스에 대 한 논리적 이름입니다. 리소스를 로드 하는 데 사용 되는 이름입니다. 기본값은 파일의 이름입니다. 인지 공용 또는 개인 어셈블리 매니페스트에 예를 들어 지정할 수 있습니다: `/linkres:filename.res,myname.res,public`합니다. 기본적으로 `filename` 는 어셈블리에 공개 합니다.  
  
## <a name="remarks"></a>주의  
 `/linkresource` 옵션 출력 파일에 리소스 파일을 포함 하지 않습니다; 사용 된 `/resource` 이 작업을 수행 하는 옵션입니다.  
  
 `/linkresource` 옵션 중 하나를 사용 하려면는 `/target` 이외의 옵션 `/target:module`합니다.  
  
 경우 `filename` 는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 만들어진 리소스 파일, 예를 들어, 여는 [Resgen.exe (리소스 파일 생성기)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) 또는 개발 환경에서의 멤버와 액세스할 수 있습니다는 <xref:System.Resources>네임 스페이스.</xref:System.Resources> (자세한 내용은 참조 <xref:System.Resources.ResourceManager>.)</xref:System.Resources.ResourceManager> 로 시작 하는 메서드를 사용 하 여 런타임 시 다른 모든 리소스에 액세스 하려면 `GetManifestResource` <xref:System.Reflection.Assembly>클래스</xref:System.Reflection.Assembly> 에서  
  
 모든 파일 형식 파일 이름일 수 있습니다. 예를 들어 다음 전역 어셈블리 캐시에 설치 및 어셈블리의 관리 되는 코드에서 액세스할 수 있도록 하는 어셈블리의 네이티브 DLL 부분 하는 것이 좋습니다.  
  
 약식 `/linkresource` 는 `/linkres`합니다.  
  
> [!NOTE]
>  `/linkresource` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다; 사용할 수는 명령줄에서 컴파일할 때만 합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb` 리소스 파일에 대 한 링크 `Rf.resource`합니다.  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
