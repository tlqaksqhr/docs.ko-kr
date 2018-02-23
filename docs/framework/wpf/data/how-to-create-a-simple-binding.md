---
title: "방법: 단순 바인딩 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a595f255b014e08b4b5b2036a7b1940e46df268f
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2018
---
# <a name="how-to-create-a-simple-binding"></a>방법: 단순 바인딩 만들기
이 예제에서는 간단한을 만드는 방법을 보여 줍니다. <xref:System.Windows.Data.Binding>합니다.  
  
## <a name="example"></a>예  
 이 예에서 한는 `Person` 라는 문자열 속성이 있는 개체 `PersonName`합니다. `Person` 개체가 라는 네임 스페이스에 정의 된 `SDKSample`합니다.  
  
 포함 하는 강조 표시 된 줄의 `<src>` 다음 예제에서 요소를 인스턴스화하는 `Person` 개체는 `PersonName` 속성 값이 `Joe`합니다. 이 작업은 `Resources` 섹션 및 할당 된 `x:Key`합니다.  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 포함 하는 강조 표시 된 줄의 `<TextBlock>` 요소 다음 바인딩합니다는 <xref:System.Windows.Controls.TextBlock> 컨트롤을 `PersonName` 속성입니다. 결과적으로 <xref:System.Windows.Controls.TextBlock> "Joe" 값으로 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
