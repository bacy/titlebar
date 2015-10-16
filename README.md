# titlebar
一个简单易用的导航栏TitleBar，可以轻松实现IOS导航栏的各种效果
整个代码全部集中在TitleBar.java中，所有控件都动态生成，动态布局。不需要引用任何资源文件，拷贝TitleBar.java到自己工程即可使用
![alt text](http://7xnkdt.com1.z0.glb.clouddn.com/pic.png "Title")
####1. 左边文字，左边返回图片，左边点击事件
######左边可设置图片，文字单独显示，也可以设置图片文字同时显示
    titleBar.setLeftImageResource(R.mipmap.back_green);
    titleBar.setLeftText("返回");
    titleBar.setLeftTextColor(Color.WHITE);
    titleBar.setLeftClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            finish();
        }
    });
####2. 中间文字
######中间文字根据左右控件始终居中显示，自动排版
    titleBar.setTitle("文章详情");
    titleBar.setTitleColor(Color.WHITE);
####3. 右边action按钮或者文字
######通过addAction添加操作控件，通过removeAction删除控件。可以使用图片或者文字。
    titleBar.setActionTextColor(Color.WHITE);
    mCollectView = (ImageView) titleBar.addAction(new TitleBar.ImageAction(R.mipmap.collect) {
        @Override
        public void performAction(View view) {
            Toast.makeText(MainActivity.this, "点击了收藏", Toast.LENGTH_SHORT).show();
            mCollectView.setImageResource(R.mipmap.fabu);
        }
    });

    titleBar.addAction(new TitleBar.TextAction("发布") {
        @Override
        public void performAction(View view) {
            Toast.makeText(MainActivity.this, "点击了发布", Toast.LENGTH_SHORT).show();
        }
    });
####4. 下划分割线
    titleBar.setDividerColor(Color.GRAY);
####5. 一行代码适配沉浸式
######如果你的项目使用了沉浸式，布局时候加上这行代码，TitleBar会自动填充状态栏
    titleBar.setImmersive(true);
