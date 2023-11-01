<h1>Hw3</h1>
    
```swift

import SwiftUI

struct TitleView: View {
    var body: some View {
        VStack(alignment: .center, spacing: 2){
            Text("1071413的").font(.system(size:30))
            Text("冰箱").font(.title).foregroundColor(.blue).bold()
        }
    }
}
extension UIScreen{
    static let screenWidth=UIScreen.main.bounds.size.width   
}
struct FoodView: View {
    var imageName:String
    var body: some View {
        VStack{
            Image(imageName).resizable().aspectRatio(contentMode: .fit).frame(width: UIScreen.screenWidth/2 , alignment: .center)
            Text(imageName.capitalized).fontWeight(.bold).font(.system(size:20))
        }.padding(.all,2)
        .frame(minWidth: 0, idealWidth: 100, maxWidth: .infinity, minHeight: 100, idealHeight: 0, maxHeight: .infinity, alignment: .center)
    }
}
struct FishView: View {
    var body: some View {
        VStack{
            Image("Octopus").resizable().aspectRatio(contentMode: .fit)
            Text("Octopus").fontWeight(.bold)
        }
    }
}

struct ContentView: View {
    var body: some View {
        VStack{
            TitleView()
            HStack{
                FoodView(imageName: "Taco")
                FoodView(imageName: "Pizza")
                FoodView(imageName: "Pork")
            }
            HStack{
                FoodView(imageName: "Orange")
                FoodView(imageName: "Juice")
            }
            ZStack{
                FishView()
                Text("做成章魚燒").background(Color.red).opacity(0.5).offset(x:0,y:50)
            }
        }
    }
}

```

<img width="40%"  src="https://raw.githubusercontent.com/hello9595/yzu-swiftui-1071413/main/hw3_screenshot.jpg?token=GHSAT0AAAAAACJW3YXIHNO6GCFC7HIZW35GZKCDREA">
