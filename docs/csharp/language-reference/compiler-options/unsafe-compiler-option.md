---
title: "-unsafe(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.assetid: fdb77ed9-da03-45bd-bb7f-250704da1bcc
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 146977522b400418a26f6a83e1a0ccdca8675bf9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="unsafe-c-compiler-options"></a>/unsafe(C# 컴파일러 옵션)
**/unsafe** 컴파일러 옵션을 사용하면 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드를 사용하는 코드를 컴파일할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```console  
/unsafe  
```  
  
## <a name="remarks"></a>설명  
 안전하지 않은 코드에 대한 자세한 내용은 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)를 참조하세요.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **안전하지 않은 코드 허용** 확인란을 선택합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>을 참조하십시오.  
  
## <a name="example"></a>예제  
 안전하지 않은 모드에 대해 `in.cs` 컴파일:  
  
```console  
csc /unsafe in.cs  
```  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)  
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
