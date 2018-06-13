---
title: -codepage(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 04a0d3a62ebd2b3a938445995725994d72d5bd4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216927"
---
# <a name="-codepage-c-compiler-options"></a>-codepage(C# 컴파일러 옵션)
이 옵션은 필수 페이지가 시스템에 대한 현재 기본 코드 페이지가 아닌 경우 컴파일 중에 사용할 코드 페이지를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>인수  
 `id`  
 컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지의 ID입니다.  
  
## <a name="remarks"></a>설명  
 컴퓨터의 기본 코드 페이지를 사용하도록 생성되지 않은 소스 코드 파일을 하나 이상 컴파일할 경우 **-codepage** 옵션을 통해 사용할 코드 페이지를 지정할 수 있습니다. **-codepage**는 컴파일에 포함된 모든 소스 코드 파일에 적용됩니다.  
  
 소스 코드 파일이 컴퓨터에 적용된 것과 동일한 코드 페이지를 사용하여 생성되었거나 소스 코드 파일이 UNICODE 또는 UTF-8을 사용하여 생성된 경우에는 **-codepage**를 사용할 필요가 없습니다.  
  
 시스템에서 지원되는 코드 페이지를 찾는 방법에 대한 자세한 내용은 [GetCPInfo](https://msdn.microsoft.com/library/dd318078(VS.85).aspx)를 참조하세요.  
  
 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)  
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
