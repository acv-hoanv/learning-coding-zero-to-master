
# React Navtive
# React Native Release Log https://github.com/react-native-community/releases/blob/master/CHANGELOG.md
# Hermes
# 0.60.1
- Add Hermes JavaScript Engine  ( https://facebook.github.io/react-native/docs/hermes )
+ Only support in Android
#  0.60.2
-Add Hermess in Android
in android/app/build.gradle add :

project.ext.react = [
entryFile: "index.js",
-     enableHermes: false  // clean and rebuild if changing
+     enableHermes: true  // clean and rebuild if changing
]

Next, if you've already built your app at least once, clean the build:
cd android && ./gradlew clean
That's it! You should now be able to develop and deploy your app as normal:
$ react-native run-android

A HermesInternal global variable will be available in JavaScript that can be used to verify that Hermes is in use:
const isHermes = () => global.HermesInternal != null;

To see the benefits of Hermes, try making a release build/deployment of your app to compare. For example:
$ react-native run-android --variant release

Debugging Hermes using Google Chrome's DevTools:
switch to localhost:8081

# 0.60.3

This is a patch release that fixes the binary path to Hermes package, thanks to @zoontek for creating the PR!

You can participate to the conversation for the next patch release in the dedicated issue.

# 0.60.4

This is a patch release that contains two more Hermes related fixes, thanks to the contributors for helping improving the support!

Generate correct source map if hermes not enabled (b1f81be by @HazAT)
Generate source maps outside of assets/ (60e75dc by @motiz88)
You can participate to the conversation for the next patch release in the dedicated issue.


# Note Hermess
- Just support  with build file apk and not support buill bundle file (.abb) 



# AndroidX
-Để convert code tự động khi sử dụng thư viên thứ 3 sử dụng jetifier:
https://github.com/mikehardy/jetifier

- Trên android nếu sử dụng enableJetifier = true thì sẽ chỉ có tác dụng với native code không có tác dụng với thư viênj thứ
3 trên react native

# React Native Firebase FCM
- Link config example https://medium.com/@katharinep/firebase-notification-integration-in-react-native-0-60-3a8d6c8d56ff

# Rename  Unsafe Lifecycles https://reactjs.org/blog/2019/08/08/react-v16.9.0.html
cd your_project
npx react-codemod rename-unsafe-lifecycles

- Khi chạy lệnh npx react-codemod rename-unsafe-lifecycles tất cả các lifecycles (componentWillMount, componentWillReceiveProps) sẽ tự thay thế bằng tên (UNSAFE_componentWillMount,UNSAFE_componentWillReceiveProps)

#React Hooks https://reactjs.org/docs/hooks-reference.html
npm install eslint-plugin-react-hooks --save-dev
eslint-plugin-react-hooks giúp chúng ta có thể tuân thủ quy tắc của Hook 

# HOOK
- Quy tắc khi sử dụng Hook:
+ Chỉ được sử dụng ở cấp cao nhất. Không được sử dụng Hook trong vòng lặp, điều kiện hoặc bên trong một hàm lồng nhau.

+ rules Hook exhaustive-deps  https://github.com/facebook/react/issues/14920

# Bắt và kiểm soát lỗi React-Native Error Boundaries
https://reactjs.org/docs/error-boundaries.html

