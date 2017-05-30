---
title: "-filealign(C# 컴파일러 옵션) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /filealign
dev_langs:
- CSharp
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 83569fa264ba3ed6e271281885940a70a5354840
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="filealign-c-compiler-options"></a>/filealign(C# 컴파일러 옵션)
**/filealign** 옵션을 사용하여 출력 파일의 섹션 크기를 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a>인수  
 `number`  
 출력 파일의 섹션 크기를 지하는 값입니다. 유효한 값은 512, 1024, 2048, 4096 및 8192입니다. 이러한 값은 바이트 단위입니다.  
  
## <a name="remarks"></a>주의  
 각 섹션은 **/filealign** 값의 배수인 경계에 맞춰지며, 고정된 기본값이 없습니다. **/filealign**을 지정하지 않으면 공용 언어 런타임에서 컴파일 시간에 기본값을 선택합니다.  
  
 섹션 크기를 지정하면 출력 파일의 크기에 영향을 줍니다. 섹션 크기를 수정하면 더 작은 장치에서 실행되는 프로그램에 유용할 수 있습니다.  
  
 출력 파일의 섹션에 대한 정보를 확인하려면 [DUMPBIN](https://docs.microsoft.com/cpp/build/reference/dumpbin-options)을 사용하세요.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **고급** 단추를 클릭합니다.  
  
4.  **파일 맞춤** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
