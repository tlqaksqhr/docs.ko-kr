---
title: ".NET Framework 4.7의 런타임 변경 내용 | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes,.NET Framework
- runtime changes,.NET Framework 4.7
- application compatibility
ms.assetid: 268eb334-7906-4e0b-a1e3-c74b745de2a5
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 321ec8f8293afad0f3da7fb6f907f45d404394cc
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-47"></a>.NET Framework 4.7의 런타임 변경 내용

드문 경우지만 런타임 변경 내용이 이전 버전의 .NET Framework를 대상으로 하지만 이후 버전의 .NET Framework 런타임에서 실행되는 기존 앱에 영향을 줄 수 있습니다. 서로 다른 .NET Framework 런타임 환경에서 실행되는 응용 프로그램 간의 동작 차이도 포함됩니다. .NET Framework 4.6.2는 다음과 같은 영역이 변경되었습니다.

- [WPF(Windows Presentation Foundation)](#WPF)

다음 테이블의 범위 열에는 각 변경 내용의 영향력이 지정되어 있습니다.

- 주요함 다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다. 이 범주에 속한 대상 다시 지정 변경 내용은 없습니다.

- 사소함 소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.

- 특별한 경우 일반적이지 않은 매우 특별한 시나리오의 앱에 영향을 주는 변경 내용입니다.

- 투명 앱 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다. 이 변경 내용으로 인한 앱 수정은 필요하지 않습니다.

## <a name="a-namewpf--windows-presentation-foundation-wpf"></a><a name="WPF" /> WPF(Windows Presentation Foundation)

assetId:///M:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView(System.Int32)?qualifyHint=False&autoUpgrade=True

| 기능 | 변경 | 영향 | 범위 |
|---|---|---|---|
| <xref:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView%2A> 메서드 | NET Framework 4.6.2에서 <xref:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView%2A> 메서드는 열 가상화가 사용되도록 설정되어 있으나 열 너비를 결정되지 않았을 때 비동기적으로 실행됩니다. 비동기 작업이 완료된 후에 열이 제거되면 <xref:System.ArgumentOutOfRangeException>이 발생할 수 있습니다.<br/></br>.NET Framework 4.7 부터는 이 시나리오에서 더 이상 예외가 throw되지 않습니다. | 이 변경은 메서드의 안정성을 향상시킵니다. | Microsoft Edge | 
|<xref:System.Windows.Controls.Ribbon.RibbonGroup> 배경 | .NET Framework 4.6.2 및 이전 버전에서 지역화된 빌드의 <xref:System.Windows.Controls.Ribbon.RibbonGroup> 배경은 투명한 브러시로 그려졌으므로 UI 환경이 좋지 않았습니다. .NET Framework 4.7에서 WPF는 <xref:System.Windows.Controls.Ribbon.RibbonGroup> 컨트롤에 대한 지역화된 리소스를 업데이트하여 올바른 브러시가 선택되도록 합니다. | 새 동작을 활용하려면 .NET Framework 4.7로 업그레이드합니다. | Microsoft Edge |
| WPF 맞춤법 검사기 | .NET Framework 4.6.1부터 WPF 응용 프로그램의 맞춤법 검사기가 응용 프로그램 종료 동안 가끔씩 <xref:System.ObjectDisposedException>을 throw합니다. <br/><br/>.NET Framework 4.7에서는 런타임에 이 예외가 정상적으로 처리되므로 응용 프로그램이 더 이상 부정적인 영향을 받지 않습니다. 디버거에서 실행 중인 응용 프로그램에서 경우에 따라 첫째 예외만 계속 확인됩니다.  | 새 동작을 활용하려면 .NET Framework 4.7로 업그레이드합니다.   | Microsoft Edge |

## <a name="see-also"></a>참고 항목

[.NET Framework 4.7의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-7.md)


