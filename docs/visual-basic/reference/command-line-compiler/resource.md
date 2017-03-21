---
title: "/resource (Visual Basic) | Microsoft 문서"
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
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: b46800322fd03eb2578cc558cc1d9bb78550aa61
ms.lasthandoff: 03/13/2017

---
# <a name="resource-visual-basic"></a>/resource(Visual Basic)
관리되는 리소스를 어셈블리에 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|필수 요소. 출력 파일에 포함할 리소스 파일의 이름입니다. 기본적으로 `filename` 는 어셈블리에 공개 합니다. 파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.|  
|`identifier`|선택적 요소. 리소스;에 대 한 논리적 이름 로드 하는 데 사용 하는 이름입니다. 기본값은 파일의 이름입니다. 리소스 인지 공용 또는 개인 어셈블리 매니페스트에 다음와 같이 지정할 수 있습니다: `/res:``filename.res`,`myname.res`,`public`|  
  
## <a name="remarks"></a>주의  
 사용 하 여 `/linkresource` 출력 파일에 리소스 파일을 배치 하지 않고 어셈블리에는 리소스를 연결 합니다.  
  
 경우 `filename` 는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 만들어진 리소스 파일, 예를 들어, 여는 [Resgen.exe (리소스 파일 생성기)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) 또는 개발 환경에서의 멤버와 액세스할 수 있습니다는 <xref:System.Resources>네임 스페이스 (참조 <xref:System.Resources.ResourceManager>자세한 내용은).</xref:System.Resources.ResourceManager> </xref:System.Resources> 런타임 시 다른 모든 리소스에 액세스 하려면 다음 방법 중 하나를 사용 합니다. <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, 또는 <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</xref:System.Reflection.Assembly.GetManifestResourceStream%2A> </xref:System.Reflection.Assembly.GetManifestResourceNames%2A> </xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>  
  
 약식 `/resource` 는 `/res`합니다.  
  
 설정 하는 방법에 대 한 내용은 `/resource` Visual Studio IDE에서 참조 [응용 프로그램 리소스 관리 (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet)합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb` 및 연결 합니다. 리소스 파일 `Rf.resource`합니다.  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)   
 [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
