---
title: "Storeadm.exe(격리된 저장소 도구) | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
caps.latest.revision: 17
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: fe899da93ea007a0ca6d590f4ae3ef69e55f55a2
ms.contentlocale: ko-kr
ms.lasthandoff: 06/02/2017

---
# <a name="storeadmexe-isolated-storage-tool"></a>Storeadm.exe(격리된 저장소 도구)
격리된 저장소 도구를 사용하면 현재 사용자의 기존 저장소를 모두 표시하거나 제거할 수 있습니다.  
  
 이 도구는 자동으로 Visual Studio와 함께 설치됩니다. 이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다. 자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.  
  
 명령 프롬프트에 다음을 입력합니다.  
  
## <a name="syntax"></a>구문  
  
```  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|옵션|설명|  
|------------|-----------------|  
|**/h**[**elp**]|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|**/list**|현재 사용자의 기존 저장소를 모두 표시합니다. 여기에는 해당 사용자가 실행한 모든 응용 프로그램 또는 어셈블리의 저장소가 포함됩니다.|  
|**/machine**|컴퓨터 저장소를 선택합니다. 이 옵션을 **/list** 또는 **/remove** 옵션과 함께 사용하면 해당 작업이 컴퓨터 저장소에 적용되도록 지정할 수 있습니다.<br /><br /> .NET Framework 2.0에 새로 추가된 옵션입니다.|  
|**/quiet**|자동 모드를 지정합니다. 오류 메시지만 표시되도록 자세한 정보는 출력하지 않습니다.|  
|**/remove**|현재 사용자의 기존 저장소를 모두 영구 제거합니다.|  
|**/roaming**|로밍 저장소를 선택합니다. 이 옵션을 **/list** 또는 **/remove** 옵션과 함께 사용하면 해당 작업이 로밍 저장소에 적용되도록 지정할 수 있습니다.|  
|**/?**|이 도구의 명령 구문 및 옵션을 표시합니다.|  
  
## <a name="remarks"></a>설명  
 아무 옵션도 지정하지 않고 명령줄에서 Storeadm.exe를 실행하면 이 도구의 구문 및 옵션이 표시됩니다.  
  
 **/list** 옵션 및 **/remove** 옵션은 일반적으로 한 번에 하나만 사용되지만 둘 이상의 옵션을 지정한 경우에는 명령줄에 표시된 순서대로 수행됩니다.  
  
 응용 프로그램에서는 두 개의 사용자용 저장소 중 하나 또는 컴퓨터 저장소를 선택하여 저장할 수 있습니다.  
  
-   로컬 저장소는 해당 사용자에 대해 사용자 데이터 로밍이 사용되는 경우에도 로밍되지 않는 위치에 있습니다(Windows 2000 이상의 경우).  
  
-   로밍 저장소는 로밍할 수 있는 위치에 있지만 Windows NT 관리를 통해 해당 사용자에 대해 로밍이 사용되는 경우에만 로밍할 수 있습니다.  
  
-   컴퓨터 저장소는 컴퓨터의 모든 사용자에게 공통적이며 해당 컴퓨터의 공용 디렉터리에 저장됩니다.  
  
    > [!NOTE]
    >  컴퓨터 저장소는 .NET Framework 버전 2.0에서 새로 도입되었습니다.  
  
 사용자에 대해 로밍이 실제로 사용되는지 여부는 Storeadm.exe의 관리에 영향을 주지 않습니다. 옵션 없이 이 도구를 실행하면 모든 작업이 로컬 저장소에 적용됩니다. **/roaming** 옵션을 지정하여 이 도구를 실행하면 모든 작업이 로밍 가능한 저장소에 적용됩니다. **/machine** 옵션을 지정하여 이 도구를 실행하면 모든 작업이 컴퓨터 저장소에 적용됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [도구](../../../docs/framework/tools/index.md)   
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)   
 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

