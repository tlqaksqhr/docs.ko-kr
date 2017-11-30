---
title: "WPF 응용 프로그램에 대해 RealTimeStylus를 사용하지 않도록 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01a4d8f6d98eb341021442d9b7964816dd673374
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>WPF 응용 프로그램에 대해 RealTimeStylus를 사용하지 않도록 설정
Windows Presentation Foundation (WPF) 기본적으로 지 원하는 Windows 7 터치식 입력을 처리 합니다. 지원 제공으로 태블릿 플랫폼의 실시간 스타일러스 입력을 통해 <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, 및 <xref:System.Windows.UIElement.OnStylusMove%2A> 이벤트입니다. 또한 Windows 7으로 Win32 WM_TOUCH 창 메시지 멀티 터치 입력을 제공합니다. 이러한 두 Api는 같은 HWND에서 함께 사용할 수 없습니다. 사용 하지 않도록 설정 WM_TOUCH 메시지 태블릿 플랫폼 (WPF 응용 프로그램에 대 한 기본값)을 통해 터치 입력 합니다. 결과적으로, WM_TOUCH WPF 창에서 터치 메시지를 받을 사용 하려면 WPF의 기본 제공 스타일러스 지원이 해제 해야 합니다. WM_TOUCH를 사용 하는 구성 요소를 호스팅하는 WPF 창과 같은 시나리오에서 적용 됩니다.  
  
 스타일러스 입력을 수신 대기 하는 WPF를 사용 하지 않도록 하려면 WPF 창에 추가 된 태블릿 지원을 제거 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플 코드는 리플렉션을 사용 하 여 기본 태블릿 플랫폼 지원을 제거 하는 방법을 보여 줍니다.  
  
```  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [스타일러스에서 입력 가로채기](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
