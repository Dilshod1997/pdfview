# Android PDF Reader 
Android Studio dan foydalangan  holda PDF Reader yaratish (java tilida). Bu dasturda xotiradagi pdf fayllarni o'qib olib foydalanuvchiga ko'rsatish.
kutubxonalardan foydalanish uchun link pastda
# 1-qadam 
build.gradle (Project) ga qo'shib qo'ying 

       maven { url "https://jitpack.io"}
         
# 2-qadam
build.gradle (Module) ga qo'shib qo'ying

    implementation 'com.github.barteksc:android-pdf-viewer:2.8.2'
    
# 3-qadam
activity.xml   ga yuklang

    <com.github.barteksc.pdfviewer.PDFView
        android:id="@+id/pdfView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>


# 4-qadam
![image](https://user-images.githubusercontent.com/46724332/111953235-950ea780-8aa3-11eb-8734-1a36a19fbd76.png)

# 5-qadam

PDFView pdfView = findViewById(R.id.pdfView);


        pdfView.fromAsset("file.pdf")
                .password(null)
                .defaultPage(0)
                .enableSwipe(true)
                .swipeHorizontal(false)
                .enableDoubletap(true)
                .onDraw(new OnDrawListener() {
                    @Override
                    public void onLayerDrawn(Canvas canvas, float pageWidth, float pageHeight, int displayedPage) {

                    }
                })
                .onDrawAll(new OnDrawListener() {
                    @Override
                    public void onLayerDrawn(Canvas canvas, float pageWidth, float pageHeight, int displayedPage) {

                    }
                })
                .onPageError(new OnPageErrorListener() {
                    @Override
                    public void onPageError(int page, Throwable t) {

                    }
                })
                .onPageChange(new OnPageChangeListener() {
                    @Override
                    public void onPageChanged(int page, int pageCount) {

                    }
                })

                .onTap(new OnTapListener() {
                    @Override
                    public boolean onTap(MotionEvent e) {
                        return true;
                    }
                })
                .onRender(new OnRenderListener() {
                    @Override
                    public void onInitiallyRendered(int nbPages, float pageWidth, float pageHeight) {
                        pdfView.fitToWidth();
                    }
                })
                .enableAnnotationRendering(true)
                .invalidPageColor(Color.WHITE)
                .load();

