此处的BitmapFactory.decodeStream，将流转化为图片，       
compress方法存储      
放入本地并通知视图库更新。     
           
           
           
           //获取流
            InputStream in = body.byteStream();
            //转化为bitmap
            Bitmap bitmap = BitmapFactory.decodeStream(in);
            
            FileOutputStream fos = new FileOutputStream(file);
            mBitmap.compress(Bitmap.CompressFormat.JPEG, 100, fos);
            
            
        // 第二步：其次把文件插入到系统图库
        try {
            MediaStore.Images.Media.insertImage(context.getContentResolver(), file.getAbsolutePath(), fileName, null);
//   /storage/emulated/0/Boohee/1493711988333.jpg
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }

        // 第三步：最后通知图库更新
        context.sendBroadcast(new Intent(Intent.ACTION_MEDIA_SCANNER_SCAN_FILE, Uri.parse("file://" + file)));
        //context.sendBroadcast(new Intent(Intent.ACTION_MEDIA_SCANNER_SCAN_FILE, Uri.fromFile(file)));
    }
