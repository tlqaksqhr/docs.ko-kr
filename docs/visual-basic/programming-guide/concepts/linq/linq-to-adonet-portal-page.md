---
title: "LINQ to ADO.NET (포털 페이지) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5c71b304dbff960320b1a9f46e38259705b8dadc
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET(포털 페이지)
[!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)]열거 가능한 개체를 쿼리할 수 있도록 [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] 를 사용 하 여는 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] 프로그래밍 모델입니다.  
  
> [!NOTE]
>  [!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)] 설명서는.NET Framework SDK의 ADO.NET 섹션에 있는: [LINQ 및 ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)합니다.  
  
 ADO.NET에는 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)], [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)] 및 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]의 세 가지 독립적인 [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)] 기술이 있습니다. [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)]다양 한 최적화 된 쿼리를 통해 제공 된 <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] 직접 쿼리할 수 있습니다 [!INCLUDE[ssNoVersion](../../../../csharp/programming-guide/concepts/linq/includes/ssnoversion_md.md)] 데이터베이스 스키마를 및 [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)] 쿼리할 수 있습니다는 [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)].</xref:System.Data.DataSet>  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet>에서 가장 널리 사용 되는 구성 요소 중 하나인 [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)], 하 고는 연결 되지 않은 프로그래밍의 핵심 요소 모델링 하는 [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] 기반으로 합니다.</xref:System.Data.DataSet> 그러나이 함에도 불구 하 고는 <xref:System.Data.DataSet>의 쿼리 기능은 제한 됩니다.</xref:System.Data.DataSet>  
  
 [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)]다양 한 쿼리 기능을 빌드할 수 있도록 <xref:System.Data.DataSet>다른 많은 데이터 소스에 사용할 수 있는 동일한 쿼리 기능을 사용 하 여.</xref:System.Data.DataSet>  
  
 자세한 내용은 참조 [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)합니다.  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]은 관계형 데이터를 개체로 관리하는 데 필요한 런타임 인프라를 제공합니다. 
          [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]에서 관계형 데이터베이스의 데이터 모델은 개발자의 프로그래밍 언어로 표현되는 개체 모델에 매핑됩니다. 응용 프로그램을 실행 하면 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] 개체 모델에 대 한 통합 언어 쿼리를 SQL로 변환 하 고 실행을 위해 데이터베이스에 전달 합니다. 데이터베이스에서 결과 반환 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] 조작할 수 있는 개체로 다시 변환 합니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]저장된 프로시저 및 데이터베이스의 사용자 정의 함수에 대 한 상속 지원 개체 모델에 포함 됩니다.  
  
 자세한 내용은 참조 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)합니다.  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)]을 통해 관계형 데이터는 .NET 환경에서 개체로 제공됩니다. 이를 통해 개체 계층은 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 지원을 위한 이상적인 대상이 되므로 개발자는 비즈니스 논리를 개발할 때 사용한 언어로 데이터베이스에 대한 쿼리를 작성할 수 있습니다. 이러한 기능은 [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)]로 알려져 있습니다. 참조 [LINQ to Entities](http://msdn.microsoft.com/library/641f9b68-9046-47a1-abb0-1c8eaeda0e2d) 에 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ 및 ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)   
 [언어 통합 쿼리 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
