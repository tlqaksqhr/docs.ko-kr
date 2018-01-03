---
title: "방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 68a28e25cf07ec3d84cc7bb12734594ca55e7e0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a>방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정
[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 사용하여 엔터티 클래스를 만들거나 사용자 지정할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../../../../../includes/vsprvs-md.md)] 코드 편집기를 사용하여 사용자 고유의 매핑 코드를 작성하거나 이미 생성된 코드를 사용자 지정할 수도 있습니다. 자세한 내용은 참조 [특성 기반 매핑](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)합니다.  
  
 이 단원의 항목에서는 개체 모델을 사용자 지정하는 방법에 대해 설명합니다.  
  
 [방법: 데이터베이스 이름 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>를 사용하는 방법을 설명합니다.  
  
 [방법: 클래스로 테이블 표현](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <xref:System.Data.Linq.Mapping.TableAttribute>를 사용하는 방법을 설명합니다.  
  
 [방법: 클래스 멤버로 열 표현](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <xref:System.Data.Linq.Mapping.ColumnAttribute>를 사용하는 방법을 설명합니다.  
  
 [방법: 기본 키 표현](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>를 사용하는 방법을 설명합니다.  
  
 [방법: 데이터베이스 관계 매핑](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <xref:System.Data.Linq.Mapping.AssociationAttribute> 특성을 사용한 예제를 제공합니다.  
  
 [방법: 데이터베이스 생성 값으로 열 표현](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>를 사용하는 방법을 설명합니다.  
  
 [방법: 타임스탬프 또는 버전 열로 열 표현](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>를 사용하는 방법을 설명합니다.  
  
 [방법: 데이터베이스 데이터 형식 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>를 사용하는 방법을 설명합니다.  
  
 [방법: 계산 열 표현](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>를 사용하는 방법을 설명합니다.  
  
 [방법: 전용 저장소 필드 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>를 사용하는 방법을 설명합니다.  
  
 [방법: NULL 값을 허용하도록 열 표현](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>를 사용하는 방법을 설명합니다.  
  
 [방법: 상속 계층 구조 매핑](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 상속 계층 구조를 지정할 수 있는 매핑하는 방법에 대해 설명합니다.  
  
 [방법: 동시성 충돌 확인 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>를 사용하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
