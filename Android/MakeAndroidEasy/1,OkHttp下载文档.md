okhttp的标准代码，去官网上搞定    

is = response.body().byteStream();首先，将取出来的东西byteStream，

FileOutputStream：需要一个一个file对象，来初始化FileOUtputStream，

基本代码：

byte[] buf = new byte[2048];
                int len = 0;
                FileOutputStream fos = null;
 
                //储存下载文件的目录
                File dir = new File(destFileDir);
                if (!dir.exists()) {
                    dir.mkdirs();
                }
                File file = new File(dir, destFileName);
 
                try {
                    is = response.body().byteStream();
                    fos = new FileOutputStream(file);
                    while ((len = is.read(buf)) != -1) {
                        fos.write(buf, 0, len);
                    }
                    fos.flush();
