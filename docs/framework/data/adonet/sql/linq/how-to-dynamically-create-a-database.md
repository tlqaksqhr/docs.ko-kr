---
title: "방법: 동적으로 데이터베이스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fb7f23c4-4572-4c38-9898-a287807d070c
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f92d34276855a7b7473dd15dd3828c4ea91c64d1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-dynamically-create-a-database"></a>방법: 동적으로 데이터베이스 만들기
LINQ to SQL에서 개체 모델은 관계형 데이터베이스에 매핑됩니다. 매핑은 특성 기반 매핑 또는 외부 매핑 파일을 사용하여 설정되며 이러한 매핑을 통해 관계형 데이터베이스의 구조를 설명할 수 있습니다. 두 경우 모두 관계형 데이터베이스에 대한 정보가 충분하므로 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드를 사용하여 데이터베이스의 새 인스턴스를 만들 수 있습니다.  
  
 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드는 개체 모델에 인코딩된 정보의 범위 내에서만 데이터베이스 복제본을 만듭니다. 개체 모델의 특성 및 매핑 파일이 기존 데이터베이스 구조에 대한 모든 사항을 인코딩하지는 않을 수도 있습니다. 매핑 정보는 사용자 정의 함수, 저장 프로시저, 트리거 또는 CHECK 제약 조건의 내용을 나타내지 않습니다. 다양한 데이터베이스에서 이 동작으로 충분합니다.  
  
 Microsoft SQL Server 2008과 같은 데이터 공급자를 사용할 수 있는 경우에는 특히 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드를 다양한 시나리오에서 사용할 수 있습니다. 일반적인 시나리오는 다음과 같습니다.  
  
-   고객 시스템에 자동으로 설치되는 응용 프로그램을 빌드하는 중입니다.  
  
-   오프라인 상태를 저장하기 위해 로컬 데이터베이스가 필요한 클라이언트 응용 프로그램을 빌드하는 중입니다.  
  
 또한 연결 문자열에 따라 .mdf 파일을 사용하거나 카탈로그 이름을 사용하여 SQL Server에서 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드를 사용할 수 있습니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 연결 문자열을 사용하여 만들려는 데이터베이스와 해당 데이터베이스를 만들 대상 서버를 정의합니다.  
  
> [!NOTE]
>  가능한 경우 연결 문자열에 암호를 사용할 필요가 없도록 Windows 통합 보안을 사용하여 데이터베이스에 연결하세요.  
  
## <a name="example"></a>예  
 다음 코드에서는 MyDVDs.mdf라는 새 데이터베이스를 만드는 방법에 대한 예를 보여 줍니다.  
  
 [!code-csharp[DLinqSubmittingChanges#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#5)]
 [!code-vb[DLinqSubmittingChanges#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#5)]  
  
## <a name="example"></a>예  
 다음과 같이 개체 모델을 사용하여 데이터베이스를 만들 수 있습니다.  
  
 [!code-csharp[DLinqSubmittingChanges#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#6)]
 [!code-vb[DLinqSubmittingChanges#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#6)]  
  
## <a name="example"></a>예  
 고객 시스템에 자동으로 설치되는 응용 프로그램을 빌드하는 경우에는 해당 데이터베이스가 이미 있는지 확인하여 새 데이터베이스를 만들기 전에 이를 삭제해야 합니다. <xref:System.Data.Linq.DataContext> 클래스는 이 프로세스를 구현하는 데 도움이 되는 <xref:System.Data.Linq.DataContext.DatabaseExists%2A> 메서드와 <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> 메서드를 제공합니다.  
  
 다음 예제에서는 이러한 메서드를 사용하여 이를 구현하는 한 가지 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqSubmittingChanges#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#7)]
 [!code-vb[DLinqSubmittingChanges#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>참고 항목  
 [특성 기반 매핑](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [외부 매핑](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [SQL-CLR 형식 매핑](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [배경 정보](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [데이터 변경 및 변경 내용 전송](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
