# titlebar
一个简单易用的导航栏TitleBar，可以轻松实现IOS导航栏的各种效果
![alt text](http://7xnkdt.com1.z0.glb.clouddn.com/pic.png "Title")

####1. 左边文字，左边返回图片，左边点击事件
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
    titleBar.setTitle("文章详情");
    titleBar.setTitleColor(Color.WHITE);
####3. 右边action按钮或者文字
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
    titleBar.setImmersive(true);
