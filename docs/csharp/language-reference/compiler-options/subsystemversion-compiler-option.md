---
title: "-subsystemversion (C# 컴파일러 옵션) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /subsystemversion(C# 컴파일러 옵션)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

실행 파일이 실행 될 수 있는 Windows 버전을 결정 하는, 생성된 된 실행 파일이 실행 될 수 있는 하위의 최소 버전을 지정 합니다. 가장 일반적으로이 옵션 하면 실행 파일의 이전 버전의 Windows에 사용할 수 없는 특정 보안 기능을 활용할 수 있습니다.  
  
> [!NOTE]
>  사용 하 여 자체 하위 시스템을 지정 하려면는 [/대상](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 컴파일러 옵션입니다.  
  
## <a name="syntax"></a>구문  
  
```  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a>매개 변수  
 `major.minor`  
 필요한 최소 버전, 하위 시스템의 주 버전과 부 버전에 대 한 점 표기법에 표현 된 대로입니다. 예를 들어 응용 프로그램 보다 오래 된 Windows 7 6.01, 하려면이 옵션의 값을 설정 하는 경우이 항목의 뒷부분에 나오는 표의 설명에 따라 운영 체제에서 실행할 수 없음을 지정할 수 있습니다. 에 대 한 값을 지정 해야 `major` 및 `minor` 정수입니다.  
  
 값은 앞에 오는 0는 `minor` 버전에는 버전은 변경 되지 않지만 후행 0입니다. 예를 들어 6.1 및 6.01 동일한 버전을 참조 하지만 6.10은 서로 다른 버전을 참조 합니다. 혼동을 피하기 위해 두 자리로 부 버전을 표현 하는 것이 좋습니다.  
  
## <a name="remarks"></a>설명  
 다음 표에서 일반적인 하위 시스템 버전의 Windows 나열합니다.  
  
|Windows 버전|하위 시스템 버전|  
|---------------------|-----------------------|  
|Windows 2000|5.00|  
|Windows XP|5.01|  
|Windows Server 2003|5.02|  
|Windows Vista|6.00|  
|Windows 7|6.01|  
|Windows Server 2008|6.01|  
|[!INCLUDE[win8](../../../csharp/language-reference/compiler-options/includes/win8_md.md)]|6.02|  
  
## <a name="default-values"></a>기본값  
 기본값은 **/subsystemversion** 컴파일러 옵션은 다음 목록에 조건에 따라 달라 집니다.  
  
-   다음 목록에서 모든 컴파일러 옵션이 설정 된 경우 기본값은 6.02:  
  
    -   [/target: appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
  
    -   [/target: winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
  
    -   [/platform:arm](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)  
  
-   기본값이 6.00 MSBuild를 사용 하는 경우, 대상으로 하 [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)], 이 목록에서 앞에 지정 된 컴파일러 옵션 중 하나를 설정 하지 않은 하 고 있습니다.  
  
-   기본값이 4.00 앞의 조건이 없는 경우 true입니다.  
  
## <a name="setting-this-option"></a>이 옵션 설정  
 설정 하는 **/subsystemversion** 컴파일러 옵션 Visual Studio에서.csproj 파일을 열 및 값을 지정 해야는 `SubsystemVersion` 는 MSBuild xml 속성입니다. Visual Studio IDE에서이 옵션을 설정할 수 없습니다. 자세한 내용은이 항목의 앞부분에 나오는 "기본값"를 참조 하거나 [일반 MSBuild 프로젝트 속성](/visual-studio/msbuild/common-msbuild-project-properties)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)