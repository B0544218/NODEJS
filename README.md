# NODEJS

### require注意事項
1. 在 Node.js 模塊系統中，如果 require 的模塊不是核心模塊，並且沒有 './' 之類的起始位置，那麼需要從當前 package 的 node_modules 裡面找，找到就到當前 package 目錄上層 node_modules 裡面取…一直找到全局node_modules目錄。
2. 對於自己創建的模塊，導入時路徑建議寫相對路徑，且不能省略./和../
3. 如果導入的路徑是個文件夾，首先檢測該文件夾下的package.json文件中main屬性對應的文件，如果存在則導入，反之如果文件不存在會報錯。如果main屬性不存在，或者package.json不存在，重啟嘗試導入文件夾下的index.js和索引.json ，如果還是沒找到，就會報錯
