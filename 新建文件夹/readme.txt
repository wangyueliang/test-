20180319 
���ܹٷ�wiki:https://github.com/arut/nginx-rtmp-module#readme
Nginx rtmp �����ص�
1.   ֧������Ƶֱ��
2.   ֧��flv/mp4��Ƶ��ʽ������������ļ�����HTTP��
3.   ֧���������ķַ�ģʽ pushand pull
4.   ���Խ�ֱ����¼�Ƴ�flv�ļ�
5.   H264/AAC����
6.   ֧������ת�� Onlinetranscoding with FFmpeg
7.   ֧��HLS (HTTP LiveStreaming)��Ҫ libavformat (>= 8. 53.31.100) from ffmpeg (ffmpeg.org)
8.   HTTPcallbacks (publish/play/record/update etc)
9.   ֧���ⲿ����(exec)
10.  HTTPcontrol module for recording audio/video and dropping clients
11.  �Ƚ��ڴ���Ƽ�����������ʹ�������ڴ����������������ֱ�����ܡ�
12.  ���Ժ�����Эͬ������FMS server��Wirecast, FMS, Wowza,��Player��JWPlayer, FlowPlayer, StrobeMediaPlayback,���ⲿ����ffmpeg,avconv,rtmpdump,flvstreamer ��
13.  Statistics in XML/XSL in machine- & human- readable form
14.  ֧�ֿ�ƽ̨ Linux/FreeBSD/MacOS


����nginx+rtmp�Ĳ��裬ʹ��centos 6.5 x64����
ע��nginx+rtmp_20180319.tar.tgz ����/opt�����ѹ��ȱ�ٿ��ļ��������������а�װ��֮��ldconfig��

pcre-8.41.tar.gz
    https://sourceforge.net/projects/pcre/files/pcre/8.41/pcre-8.41.tar.gz/download

nginx-rtmp-module-1.2.1.tar.gz
    https://codeload.github.com/arut/nginx-rtmp-module/tar.gz/v1.2.1

nginx-1.12.2.tar.gz
    http://nginx.org/download/nginx-1.12.2.tar.gz


����nginx
./configure --prefix=/opt/nginx --add-module=../nginx-rtmp-module-1.2.1  --with-http_stub_status_module


��װnginx����/opt/nginxĿ¼��
make && make install

����
./sbin/nginx


�޸�nginx.con,���¼��������ļ�
sudo ./sbin/nginx -s reload


ʹ��obs����
rtmp://192.168.12.178/live/livestream


hls����
http://192.168.12.178/live/livestream/index.m3u8


vlc����
rtmp://192.168.12.178/live/livestream



����ngixn����״̬
http://192.168.12.178/nginx_status


����rtmp����״̬
http://192.168.12.178/stat


jwplayer ֱ��rtmp
http://192.168.12.178/index.html


rtmp ����
�������
rtmp://live.hkstv.hk.lxdns.com/live/hks
ֱ��rtmp
file: "rtmp://192.168.12.178/live/livestream"
�㲥rtmp
file: "rtmp://192.168.12.178/vod/test.flv"






