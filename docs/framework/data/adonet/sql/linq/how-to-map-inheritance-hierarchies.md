---
title: "방법: 상속 계층 구조 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6a0393d11c949c0bceb6587059cd450113c0ead2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-map-inheritance-hierarchies"></a>방법: 상속 계층 구조 매핑
[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]에서 상속 매핑을 구현하려면 다음 단계의 설명과 같이 상속 계층 구조의 루트 클래스에 특성 및 특성 속성을 지정해야 합니다. [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 통해 상속 계층 구조를 매핑할 수 있습니다. 참조 [하는 방법: O/R 디자이너를 사용 하 여 상속 구성](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)합니다.  
  
> [!NOTE]
>  서브클래스에는 특수 특성 또는 속성이 필요 없습니다. 특히 서브클래스에는 <xref:System.Data.Linq.Mapping.TableAttribute> 특성이 없습니다.  
  
### <a name="to-map-an-inheritance-hierarchy"></a>상속 계층 구조를 매핑하려면  
  
1.  루트 클래스에 <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 추가합니다.  
  
2.  또한 루트 클래스에 계층 구조의 각 클래스에 대한 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성을 추가합니다.  
  
3.  각 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성에 대해 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 속성을 정의합니다.  
  
     이 속성에는 이 데이터 행이 속한 클래스 또는 서브클래스를 나타내기 위해 데이터베이스 테이블의 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 열에 표시되는 값이 저장됩니다.  
  
4.  또한 각 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성에 대해 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> 속성을 추가합니다.  
  
     이 속성에는 키 값이 의미하는 클래스 또는 서브클래스를 지정하는 값이 저장됩니다.  
  
5.  <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성 중 하나의 특성에만 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> 속성을 추가합니다.  
  
     이 속성은 지정 하는 *대체 (fallback)* 데이터베이스 테이블의 판별자 값 하나라도 일치 하지 않는 경우 매핑 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 상속 매핑의 값입니다.  
  
6.  <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 특성에 대해 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.  
  
     이 속성은 열에 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 값이 저장됨을 의미합니다.  
  
## <a name="example"></a>예제  
  
> [!NOTE]
>  [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 경우 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 통해 상속을 구성할 수 있습니다. 참조 [하는 방법: O/R 디자이너를 사용 하 여 상속 구성](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)  
  
 다음 코드 예제에서는 `Vehicle`이 루트 클래스로 정의되어 있으며 이전 단계는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 계층 구조를 설명하기 위해 구현되었습니다.  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [상속 지원](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)  
 [방법: 엔터티 클래스 코드 편집기를 사용 하 여 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
