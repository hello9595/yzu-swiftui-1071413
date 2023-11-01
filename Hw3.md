import SwiftUI

struct TitleView: View {
    var body: some View {
        VStack(alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/, spacing: 2){
            Text("1071413的").font(.system(size:30))
            Text("冰箱").font(/*@START_MENU_TOKEN@*/.title/*@END_MENU_TOKEN@*/).foregroundColor(/*@START_MENU_TOKEN@*/.blue/*@END_MENU_TOKEN@*/).bold()
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
            Image(imageName).resizable().aspectRatio(contentMode: .fit).frame(width: UIScreen.screenWidth/2 , alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
            Text(imageName.capitalized).fontWeight(/*@START_MENU_TOKEN@*/.bold/*@END_MENU_TOKEN@*/).font(.system(size:20))
        }.padding(.all,2)
        .frame(minWidth: 0, idealWidth: 100, maxWidth: /*@START_MENU_TOKEN@*/.infinity/*@END_MENU_TOKEN@*/, minHeight: 100, idealHeight: 0, maxHeight: .infinity, alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
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
