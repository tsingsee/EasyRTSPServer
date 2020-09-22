# EasyRTSPServer

EasyRTSPServer是一款是由[**TSINGSEE青犀开放平台**](http://open.tsingsee.com "TSINGSEE")团队开发和迭代的非常稳定、易用、支持多种平台（包括Windows/Linux 32&64，Android，iOS，ARM等平台）的RTSP Server组件，适用于IPCamera、NVR、编码器、安卓监控设备等软硬件产品，接口调用非常简单成熟，调用者无需关注RTSP Server中关于客户端监听接入、音视频多路复用、RTSP具体流程、RTP打包与发送等相关问题，支持多种音视频格式，再也不用像调用其他RTSPServer那样处理整个RTSP OPTIONS/DESCRIBE/SETUP/PLAY/RTP/RTCP的复杂流程和担心内存释放的问题了！EasyRTSPServer非常适合于安防领域、教育领域、互联网直播等领域；

BTW：EasyRTSPServer非常适合在海思系列芯片上运行，性能以及稳定性都非常优秀，并发方面，稳定保持在20路1080P并发：

 - TCP/UDP 方式分别连接20路下，1080P 4M 定码率，音频格式G711（64K）G726（16K 24K 32K 40K）AAC(64K 96K 128K)都没问题；
 
 - 支持Basic、Digest两种鉴权模式；


## 功能支持 ##

- [x] 标准、稳定运行的RTSP/RTP服务；
- [x] 支持RTP over UDP/RTP over TCP；
- [x] 视频编码格式支持：H.264、H.265；
- [x] 音频编码格式支持：G.711A、G.711U、G.726、AAC；
- [x] 支持标准RTSP鉴权认证;
- [x] 灵活的SDK调用接口支持;
- [x] 丰富的SDK接口调用示例;

## 调用示例 ##

- **EasyRTSPServer**：在不同的调用平台上，我们实现了不同的调用示例；
	1. Android：采集Android摄像头（支持前/后摄像头切换）和麦克风声音作为数据源的安卓RTSPServer；
	1. Windows：支持以视频文件为视频源、支持以其他IPC硬件（海康、大华、雄迈）提供的RTSP流作为数据源，再以标准RTSP服务形式对外提供RTSPServer功能；
	6. ARM上我们提供基于海思v100/v200/v300/v400以及其他ARM芯片的摄像机芯片编码后的音视频做为数据源的EasyRTSPServer，具体芯片调用demo示例代码请邮件至support@tsingsee.com申请；
	
	Windows编译方法，

    	Visual Studio 2010 编译：./EasyRTSPServer-master/EasyRTSPServer.sln

	Linux编译方法，

		chmod +x ./Buildit
		./Buildit


	<table>
	<tr><td><b>支持平台</b></td><td><b>芯片</b></td><td><b>目录位置</b></td></tr>
	<tr><td>Windows</td><td>x86</td><td>./Lib/</td></tr>
	<tr><td>Windows</td><td>x64</td><td>./Lib/x64/</td></tr>
	<tr><td>Linux</td><td>x86</td><td>./Lib/</td></tr>
	<tr><td>Linux</td><td>x64</td><td>./Lib/x64/</td></tr>
	<tr><td>Android</td><td>Android</td><td>./Android/</td></tr>
	<tr><td>海思</td><td>arm-hisiv100-linux</td><td>./Lib/hisiv100/</td></tr>
	<tr><td>海思</td><td>arm-hisiv200-linux</td><td>./Lib/hisiv200/</td></tr>
	<tr><td>海思</td><td>arm-hisiv300-linux</td><td>./Lib/hisiv300/</td></tr>
	<tr><td>海思</td><td>arm-hisiv400-linux</td><td>./Lib/hisiv400/</td></tr>
	<tr><td>海思</td><td>arm-hisiv500-linux</td><td>./Lib/hisiv500/</td></tr>
	<tr><td>海思</td><td>arm-hisiv600-linux</td><td>./Lib/hisiv600/</td></tr>
	<tr><td colspan="3"><center>邮件获取更多平台版本</center></td></tr>
	</table>


## 调用全流程

![](http://www.easydarwin.org/github/images/easyipcamera/easyipcamera20160805.gif)

### EasyRTSPServer支持数据格式说明

EASY\_SDK\_VIDEO\_FRAME\_FLAG数据可支持多种视频格式：
		
	#define EASY_SDK_VIDEO_CODEC_H265			/* H265  */
	#define EASY_SDK_VIDEO_CODEC_H264			/* H264  */
	#define	EASY_SDK_VIDEO_CODEC_MJPEG			/* MJPEG */
	#define	EASY_SDK_VIDEO_CODEC_MPEG4			/* MPEG4 */

视频帧标识支持

	#define EASY_SDK_VIDEO_FRAME_I				/* I帧 */
	#define EASY_SDK_VIDEO_FRAME_P				/* P帧 */
	#define EASY_SDK_VIDEO_FRAME_B				/* B帧 */
	#define EASY_SDK_VIDEO_FRAME_J				/* JPEG */

EASY\_SDK\_AUDIO\_FRAME\_FLAG数据可支持多种音频格式：
	
	#define EASY_SDK_AUDIO_CODEC_AAC			/* AAC */
	#define EASY_SDK_AUDIO_CODEC_G711A			/* G711 alaw*/
	#define EASY_SDK_AUDIO_CODEC_G711U			/* G711 ulaw*/
	#define EASY_SDK_AUDIO_CODEC_G726			/* G726 */


### ✈ 更多视频解决方案资源汇总

- 流媒体技术：<br/>
© EasyDarwin开源流媒体服务器：<a href="http://www.easydarwin.org" target="_blank" title="EasyDarwin开源流媒体服务器">http://www.easydarwin.org</a><br/>
© TSINGSEE视频开放平台：<a href="http://open.tsingsee.com" target="_blank" title="TSINGSEE青犀视频开放平台">http://open.tsingsee.com</a><br/>

- 视频云服务：<br/>
© EasyDSS互联网视频云服务：<a href="http://www.easydss.com" target="_blank" title="EasyDSS互联网视频云服务">http://www.easydss.com</a><br/>
© EasyCVR安防视频云服务：<a href="http://www.easycvr.com" target="_blank" title="EasyCVR安防视频云服务">http://www.easycvr.com</a><br/>
© EasyGBS国标视频云服务：<a href="http://www.easygbs.com" target="_blank" title="EasyGBS国标视频云服务">http://www.easygbs.com</a><br/>
© EasyRTC在线视频会议平台：<a href="http://www.easyrtc.cn" target="_blank" title="EasyRTC在线视频会议平台">http://www.easyrtc.cn</a><br/>
© EasyRTS即时通信云服务：<a href="http://www.easyrts.com" target="_blank" title="EasyRTS即时通信云服务">http://www.easyrts.com</a><br/>

- 边缘计算：<br/>
© EasyNVR视频边缘计算网关：<a href="http://www.easynvr.com" target="_blank" title="EasyNVR视频边缘计算网关">http://www.easynvr.com</a><br/>
© EasyNTS上云网关：<a href="http://www.easynts.com" target="_blank" title="EasyNTS上云网关">http://www.easynts.com</a><br/>

© TSINGSEE Team：<a href="http://www.tsingsee.com" target="_blank" title="青犀TSINGSEE">http://www.tsingsee.com</a><br/>
![青犀TSINGSEE](https://imgconvert.csdnimg.cn/aHR0cDovL3d3dy5lYXN5ZGFyd2luLm9yZy9wdWJsaWMvaW1hZ2VzL3RzaW5nc2VlX3FyY29kZV8xNjAuanBn?x-oss-process=image/format,png)
