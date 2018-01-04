---
title: "WF의 오류 처리 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96a868cd28823c3185d1297f7709dcfdc28a14a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="error-handling-activities-in-wf"></a>WF의 오류 처리 활동
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에서는 오류 처리 및 복구를 구현하기 위해 여러 시스템 제공 활동을 제공합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][예외](../../../docs/framework/windows-workflow-foundation/exceptions.md)합니다.  
  
## <a name="error-handling-activities"></a>오류 처리 작업  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|`TryCatch` 활동에서 throw된 마지막 예외를 다시 throw합니다.|  
|<xref:System.Activities.Statements.Throw>|예외를 throw합니다.|  
|<xref:System.Activities.Statements.TryCatch>|예외 처리를 구현합니다.|
