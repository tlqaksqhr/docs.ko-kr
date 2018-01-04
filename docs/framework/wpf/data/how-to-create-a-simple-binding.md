---
title: "방법: 단순 바인딩 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 108b532e3aea27571c8a3b1290d931e2b0769be9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-simple-binding"></a>방법: 단순 바인딩 만들기
이 예제에서는 간단한을 만드는 방법을 보여 줍니다. <xref:System.Windows.Data.Binding>합니다.  
  
## <a name="example"></a>예  
 이 예에서 한는 `Person` 라는 문자열 속성이 있는 개체 `PersonName`합니다. `Person` 개체가 라는 네임 스페이스에 정의 된 `SDKSample`합니다.  
  
 다음 예제는 `Person` 개체는 `PersonName` 속성 값이 `Joe`합니다. 이 작업은 `Resources` 섹션 및 할당 된 `x:Key`합니다.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xaml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 바인딩할는 `PersonName` 속성 다음을 수행 합니다.  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 결과적으로 <xref:System.Windows.Controls.TextBlock> "Joe" 값으로 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
