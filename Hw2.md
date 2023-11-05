<h1>Hw2</h1>
    
```swift

import SwiftUI

struct ContentView: View{
 @State var count : Int=0
    var body: some View{
        VStack{
            //Text(String(count)).padding(.all,10).frame(width: 150, height: 120, alignment: .center).font(.system(size: 100))
            if(count==0){
                Image("Paper").resizable().aspectRatio(contentMode: .fit )
            }
            else if(count==1){
                Image("Stone").resizable().aspectRatio(contentMode: .fit )
            }
            else{
                Image("scissors").resizable().aspectRatio(contentMode: .fit )
                
            }
            Button(action: {
                count = Int.random(in: 0...2)
                
                }, 
               label: {
                Text("猜拳").padding(.all,10).frame(width: 300, height: 100, alignment: .center).font(.system(size: 50)).background(Color.purple).foregroundColor(.white).border(Color.purple, width: 5).cornerRadius(20)
            })
        }
    }
}

```

<img width="40%"  src="https://github.com/hello9595/yzu-swiftui-1071413/blob/b12ca92159eee40d0ae690d3e294cbf40bc0496c/hw2-video.mp4">
