---
title: SQL 워크플로 인스턴스 저장소
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 11e61e1d702572af10cf4e46b9d1b284022fa56e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="sql-workflow-instance-store"></a>SQL 워크플로 인스턴스 저장소
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]는 워크플로가 SQL Server 2005 또는 SQL Server 2008 데이터베이스에서 워크플로 인스턴스에 대한 상태 정보를 유지할 수 있는 SQL 워크플로 인스턴스 저장소와 함께 제공됩니다. 이 기능은 주로 지속성 프레임워크의 추상 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 클래스에서 파생되는 <xref:System.Runtime.DurableInstancing.InstanceStore> 클래스의 형태로 구현됩니다. SQL 워크플로 인스턴스 저장소 기능은 호스트가 지속성 명령을 저장소에 보내는 데 사용하는 지속성 API의 구체적인 구현인 SQL 지속성 공급자를 구성합니다.  
  
 SQL 워크플로 인스턴스 저장소는 <xref:System.Activities.WorkflowApplication> 또는 <xref:System.ServiceModel.WorkflowServiceHost>를 사용하는 자체 호스팅 워크플로 또는 워크플로 서비스뿐 아니라 <xref:System.ServiceModel.WorkflowServiceHost>를 사용하여 WAS에서 호스트되는 서비스도 모두 지원합니다. 기능에 의해 노출되는 개체 모델을 사용하여 자체 호스팅 서비스에 대한 SQL 워크플로 인스턴스 저장소 기능을 프로그래밍 방식으로 구성할 수 있습니다. 개체 모델 및 XML 구성 파일을 사용하고 프로그래밍 방식으로 <xref:System.ServiceModel.WorkflowServiceHost>에 의해 호스트되는 서비스에 대해 이 기능을 구성할 수 있습니다.  
  
 SQL 워크플로 인스턴스 저장소 기능 (**SqlWorkflowInstanceStore** 클래스) 구현 하지 않는 <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> 및 지속적인 워크플로가 아닌 WCF 서비스에 대 한 지 속성 지원을 제공 하지 않습니다. 이 기능은 <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService>도 구현하지 않으므로 3.x 워크플로에 대한 지속성 지원을 제공하지 않습니다. 이 기능은 WF 4.0 이상 워크플로 및 워크플로 서비스에 대해서만 지속성을 지원하며, SQL Server 2005 및 SQL Server 2008 이외의 다른 데이터베이스를 지원하지 않습니다.  
  
 이 단원의 항목에서는 SQL 워크플로 인스턴스 저장소의 속성과 기능을 설명하고 저장소 구성에 대한 세부 정보를 제공합니다.  
  
 Windows Server AppFabric은 고유의 인스턴스 저장소 및 도구를 제공하여 구성 및 인스턴스 저장소의 사용을 단순화합니다. 자세한 내용은 참조 하십시오. 참조 [Windows Server App Fabric 인스턴스 스토어](http://go.microsoft.com/fwlink/?LinkId=201201)합니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)] App Fabric SQL Server 지 속성 데이터베이스 참조 [App Fabric SQL Server 지 속성 데이터베이스](http://go.microsoft.com/fwlink/?LinkId=201202)  
  
## <a name="in-this-section"></a>섹션 내용  
  
-   [SQL 워크플로 인스턴스 저장소의 속성](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md)  
  
-   [방법: 워크플로 및 워크플로 서비스에 SQL 지속성 사용](../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [인스턴스 활성화](../../../docs/framework/windows-workflow-foundation/instance-activation.md)  
  
-   [쿼리 지원](../../../docs/framework/windows-workflow-foundation/support-for-queries.md)  
  
-   [저장소 확장성](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)  
  
-   [보안](../../../docs/framework/windows-workflow-foundation/security.md)  
  
-   [SQL Server 지속성 데이터베이스](../../../docs/framework/windows-workflow-foundation/sql-server-persistence-database.md)  
  
## <a name="see-also"></a>참고 항목  
 [지 속성 샘플](http://go.microsoft.com/fwlink/?LinkID=177735)
