7. 获取指定id的回复和子回复
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

7.1 访问路径
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 GET /task/reply/list

7.2 逻辑
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

 获取指定id的回复和子回复

7.3 Request
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
=============== =============== =============================================
  Field Name         Type                        Description                 
=============== =============== =============================================
  reply_type        String      
--------------- --------------- ---------------------------------------------
   parent_id        String      
--------------- --------------- ---------------------------------------------
 need_extract       String      
=============== =============== =============================================

7.4 Sample Request
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

    GET /task/reply/list?reply_type=1&&parent_id=1&&need_extract=true
7.5 Response
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
=============== =============== =============================================
  Field Name         Type                        Description                 
=============== =============== =============================================
    status          String                           状态码                     
--------------- --------------- ---------------------------------------------
    message         String                          返回消息                     
--------------- --------------- ---------------------------------------------
     data       
--------------- --------------- ---------------------------------------------
      id            Number      
--------------- --------------- ---------------------------------------------
  replyUserId       Number      
--------------- --------------- ---------------------------------------------
replyUserPhoto      String      
--------------- --------------- ---------------------------------------------
 replyUserName      String      
--------------- --------------- ---------------------------------------------
    content         String      
--------------- --------------- ---------------------------------------------
    praises         Number      
--------------- --------------- ---------------------------------------------
   replyTime        String      
--------------- --------------- ---------------------------------------------
    grades          Number      
--------------- --------------- ---------------------------------------------
   firstImg         String      
--------------- --------------- ---------------------------------------------
     text           String      
--------------- --------------- ---------------------------------------------
    replies     
--------------- --------------- ---------------------------------------------
      id            Number      
--------------- --------------- ---------------------------------------------
  replyUserId       Number      
--------------- --------------- ---------------------------------------------
replyUserPhoto      String      
--------------- --------------- ---------------------------------------------
 replyUserName      String      
--------------- --------------- ---------------------------------------------
    content         String      
--------------- --------------- ---------------------------------------------
    praises         Number      
--------------- --------------- ---------------------------------------------
   replyTime        String      
--------------- --------------- ---------------------------------------------
    grades          Number      
--------------- --------------- ---------------------------------------------
   firstImg         String      
--------------- --------------- ---------------------------------------------
     text           String      
--------------- --------------- ---------------------------------------------
    replies     
--------------- --------------- ---------------------------------------------
      id            Number      
--------------- --------------- ---------------------------------------------
  replyUserId       Number      
--------------- --------------- ---------------------------------------------
replyUserPhoto      String      
--------------- --------------- ---------------------------------------------
 replyUserName      String      
--------------- --------------- ---------------------------------------------
    content         String      
--------------- --------------- ---------------------------------------------
    praises         Number      
--------------- --------------- ---------------------------------------------
   replyTime        String      
--------------- --------------- ---------------------------------------------
    grades          Number      
--------------- --------------- ---------------------------------------------
   firstImg         String      
--------------- --------------- ---------------------------------------------
     text           String      
--------------- --------------- ---------------------------------------------
    replies     
--------------- --------------- ---------------------------------------------
=============== =============== =============================================

7.6 Sample Response
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

   {
      "status": "TASK-SUCCESS-104",
      "message": "查询成功",
      "data": [
        {
          "id": 4,
          "replyUserId": 1342,
          "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
          "replyUserName": "dt123123134",
          "content": "2019年7月17日，ITU-R WP5D#32会议在巴西布济乌斯结束。来自全球政府主管部门、电信制造及运营企业、研究机构共约180名代表参加了本次会议。中国代表团主要由中国信息通信研究院、华为、中兴、中国信科、中国移动、中国电信、中国联通等单位构成。本次会议我国完成了IMT-2020（5G）候选技术方案的完整提交，获得了ITU关于5G候选技术方案的正式接收确认函。",
          "praises": 0,
          "replyTime": "2019-07-19 10:05:23",
          "grades": 10,
          "firstImg": "",
          "text": "2019年7月17日，ITU-R WP5D#32会议在巴西布济乌斯结束。来自全球政府主管部门、电信制造及运营企业、研究机构共约180名代表参加了本次会议。中国代表团主要由中国信息通信研究院、华为、中兴、中国信科、中国移动、中国电信、中国联通等单位构成。本次会议我国完成了IMT-2020（5G）候选技术方案的完整提交，获得了ITU关于5G候选技术方案的正式接收确认函。",
          "replies": [
            {
              "id": 17,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "12345",
              "praises": 0,
              "replyTime": "2019-07-22 09:46:40",
              "grades": 1,
              "firstImg": "",
              "text": "12345",
              "replies": [
                {
                  "id": 57,
                  "replyUserId": 1342,
                  "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
                  "replyUserName": "dt123123134",
                  "content": "11122",
                  "praises": 0,
                  "replyTime": "2019-07-23 13:59:32",
                  "grades": 0,
                  "firstImg": "",
                  "text": "11122",
                  "replies": []
                }
              ]
            },
            {
              "id": 23,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "666",
              "praises": 0,
              "replyTime": "2019-07-22 20:36:12",
              "grades": 0,
              "firstImg": "",
              "text": "666",
              "replies": []
            },
            {
              "id": 24,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "",
              "praises": 0,
              "replyTime": "2019-07-22 20:36:50",
              "grades": 0,
              "firstImg": "",
              "text": "",
              "replies": []
            },
            {
              "id": 36,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "    111                       ",
              "praises": 0,
              "replyTime": "2019-07-23 13:24:15",
              "grades": 0,
              "firstImg": "",
              "text": "    111                       ",
              "replies": []
            },
            {
              "id": 38,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "222",
              "praises": 0,
              "replyTime": "2019-07-23 13:33:14",
              "grades": 0,
              "firstImg": "",
              "text": "222",
              "replies": []
            },
            {
              "id": 39,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "dfdfd",
              "praises": 0,
              "replyTime": "2019-07-23 13:33:27",
              "grades": 0,
              "firstImg": "",
              "text": "dfdfd",
              "replies": []
            },
            {
              "id": 40,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "dddd",
              "praises": 0,
              "replyTime": "2019-07-23 13:33:53",
              "grades": 0,
              "firstImg": "",
              "text": "dddd",
              "replies": []
            },
            {
              "id": 56,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "111",
              "praises": 0,
              "replyTime": "2019-07-23 13:59:20",
              "grades": 0,
              "firstImg": "",
              "text": "111",
              "replies": []
            },
            {
              "id": 58,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "1119",
              "praises": 0,
              "replyTime": "2019-07-23 14:00:17",
              "grades": 0,
              "firstImg": "",
              "text": "1119",
              "replies": []
            },
            {
              "id": 59,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "1110",
              "praises": 0,
              "replyTime": "2019-07-23 14:00:33",
              "grades": 0,
              "firstImg": "",
              "text": "1110",
              "replies": []
            }
          ]
        },
        {
          "id": 5,
          "replyUserId": 1342,
          "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
          "replyUserName": "dt123123134",
          "content": "写的不错",
          "praises": 0,
          "replyTime": "2019-07-19 10:49:00",
          "grades": 14,
          "firstImg": "",
          "text": "写的不错",
          "replies": [
            {
              "id": 9,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "是",
              "praises": 0,
              "replyTime": "2019-07-19 11:52:44",
              "grades": 0,
              "firstImg": "",
              "text": "是",
              "replies": []
            },
            {
              "id": 10,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "认同",
              "praises": 0,
              "replyTime": "2019-07-19 13:42:38",
              "grades": 0,
              "firstImg": "",
              "text": "认同",
              "replies": []
            },
            {
              "id": 11,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "",
              "praises": 0,
              "replyTime": "2019-07-19 13:45:34",
              "grades": 0,
              "firstImg": "",
              "text": "",
              "replies": []
            },
            {
              "id": 25,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "hhhh",
              "praises": 0,
              "replyTime": "2019-07-22 20:41:50",
              "grades": 0,
              "firstImg": "",
              "text": "hhhh",
              "replies": []
            },
            {
              "id": 27,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "111",
              "praises": 0,
              "replyTime": "2019-07-22 21:17:52",
              "grades": 0,
              "firstImg": "",
              "text": "111",
              "replies": []
            },
            {
              "id": 28,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "1122",
              "praises": 0,
              "replyTime": "2019-07-22 21:17:54",
              "grades": 0,
              "firstImg": "",
              "text": "1122",
              "replies": []
            },
            {
              "id": 29,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "3去少奋斗",
              "praises": 0,
              "replyTime": "2019-07-22 21:17:56",
              "grades": 0,
              "firstImg": "",
              "text": "3去少奋斗",
              "replies": []
            },
            {
              "id": 30,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "水电阿斯蒂芬费",
              "praises": 0,
              "replyTime": "2019-07-22 21:18:00",
              "grades": 0,
              "firstImg": "",
              "text": "水电阿斯蒂芬费",
              "replies": []
            },
            {
              "id": 31,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "sddd",
              "praises": 0,
              "replyTime": "2019-07-22 21:18:02",
              "grades": 0,
              "firstImg": "",
              "text": "sddd",
              "replies": []
            },
            {
              "id": 32,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "ddd",
              "praises": 0,
              "replyTime": "2019-07-22 21:18:05",
              "grades": 0,
              "firstImg": "",
              "text": "ddd",
              "replies": []
            },
            {
              "id": 33,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "df dsf ",
              "praises": 0,
              "replyTime": "2019-07-22 21:18:10",
              "grades": 0,
              "firstImg": "",
              "text": "df dsf ",
              "replies": []
            },
            {
              "id": 34,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "sdf sdf ",
              "praises": 0,
              "replyTime": "2019-07-22 21:18:16",
              "grades": 0,
              "firstImg": "",
              "text": "sdf sdf ",
              "replies": []
            },
            {
              "id": 45,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "11",
              "praises": 0,
              "replyTime": "2019-07-23 13:43:21",
              "grades": 0,
              "firstImg": "",
              "text": "11",
              "replies": []
            },
            {
              "id": 46,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "11",
              "praises": 0,
              "replyTime": "2019-07-23 13:44:09",
              "grades": 0,
              "firstImg": "",
              "text": "11",
              "replies": []
            }
          ]
        },
        {
          "id": 6,
          "replyUserId": 1342,
          "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
          "replyUserName": "dt123123134",
          "content": "很好很好 赞",
          "praises": 0,
          "replyTime": "2019-07-19 11:03:00",
          "grades": 3,
          "firstImg": "",
          "text": "很好很好 赞",
          "replies": [
            {
              "id": 22,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "666",
              "praises": 0,
              "replyTime": "2019-07-22 20:35:38",
              "grades": 0,
              "firstImg": "",
              "text": "666",
              "replies": []
            },
            {
              "id": 41,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "111",
              "praises": 0,
              "replyTime": "2019-07-23 13:35:23",
              "grades": 0,
              "firstImg": "",
              "text": "111",
              "replies": []
            },
            {
              "id": 42,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "111",
              "praises": 0,
              "replyTime": "2019-07-23 13:36:28",
              "grades": 0,
              "firstImg": "",
              "text": "111",
              "replies": []
            }
          ]
        },
        {
          "id": 7,
          "replyUserId": 1342,
          "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
          "replyUserName": "dt123123134",
          "content": "赞",
          "praises": 0,
          "replyTime": "2019-07-19 11:05:48",
          "grades": 3,
          "firstImg": "",
          "text": "赞",
          "replies": [
            {
              "id": 12,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "123",
              "praises": 0,
              "replyTime": "2019-07-19 14:23:42",
              "grades": 0,
              "firstImg": "",
              "text": "123",
              "replies": []
            },
            {
              "id": 37,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "ddd",
              "praises": 0,
              "replyTime": "2019-07-23 13:24:38",
              "grades": 0,
              "firstImg": "",
              "text": "ddd",
              "replies": []
            },
            {
              "id": 55,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "11",
              "praises": 0,
              "replyTime": "2019-07-23 13:48:52",
              "grades": 0,
              "firstImg": "",
              "text": "11",
              "replies": []
            }
          ]
        },
        {
          "id": 8,
          "replyUserId": 1342,
          "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
          "replyUserName": "dt123123134",
          "content": "写的非常,赶紧学习一下",
          "praises": 0,
          "replyTime": "2019-07-19 11:08:17",
          "grades": 8,
          "firstImg": "",
          "text": "写的非常,赶紧学习一下",
          "replies": [
            {
              "id": 13,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "11",
              "praises": 0,
              "replyTime": "2019-07-19 14:23:51",
              "grades": 0,
              "firstImg": "",
              "text": "11",
              "replies": []
            },
            {
              "id": 14,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "12",
              "praises": 0,
              "replyTime": "2019-07-19 14:23:53",
              "grades": 0,
              "firstImg": "",
              "text": "12",
              "replies": []
            },
            {
              "id": 43,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "111",
              "praises": 0,
              "replyTime": "2019-07-23 13:41:46",
              "grades": 0,
              "firstImg": "",
              "text": "111",
              "replies": []
            },
            {
              "id": 44,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "dddd",
              "praises": 0,
              "replyTime": "2019-07-23 13:41:58",
              "grades": 0,
              "firstImg": "",
              "text": "dddd",
              "replies": []
            },
            {
              "id": 49,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "ddd",
              "praises": 0,
              "replyTime": "2019-07-23 13:45:06",
              "grades": 0,
              "firstImg": "",
              "text": "ddd",
              "replies": []
            },
            {
              "id": 50,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "dd",
              "praises": 0,
              "replyTime": "2019-07-23 13:45:12",
              "grades": 0,
              "firstImg": "",
              "text": "dd",
              "replies": []
            },
            {
              "id": 51,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "ddd",
              "praises": 0,
              "replyTime": "2019-07-23 13:45:22",
              "grades": 0,
              "firstImg": "",
              "text": "ddd",
              "replies": []
            },
            {
              "id": 53,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "111",
              "praises": 0,
              "replyTime": "2019-07-23 13:46:37",
              "grades": 0,
              "firstImg": "",
              "text": "111",
              "replies": []
            }
          ]
        },
        {
          "id": 18,
          "replyUserId": 1342,
          "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
          "replyUserName": "dt123123134",
          "content": "111",
          "praises": 0,
          "replyTime": "2019-07-22 11:21:55",
          "grades": 1,
          "firstImg": "",
          "text": "111",
          "replies": [
            {
              "id": 52,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "11",
              "praises": 0,
              "replyTime": "2019-07-23 13:46:12",
              "grades": 0,
              "firstImg": "",
              "text": "11",
              "replies": []
            }
          ]
        },
        {
          "id": 19,
          "replyUserId": 1342,
          "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
          "replyUserName": "dt123123134",
          "content": "hhhh",
          "praises": 0,
          "replyTime": "2019-07-22 15:01:13",
          "grades": 3,
          "firstImg": "",
          "text": "hhhh",
          "replies": [
            {
              "id": 47,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "111",
              "praises": 0,
              "replyTime": "2019-07-23 13:44:31",
              "grades": 0,
              "firstImg": "",
              "text": "111",
              "replies": []
            },
            {
              "id": 48,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "1111",
              "praises": 0,
              "replyTime": "2019-07-23 13:44:48",
              "grades": 0,
              "firstImg": "",
              "text": "1111",
              "replies": []
            },
            {
              "id": 54,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "1",
              "praises": 0,
              "replyTime": "2019-07-23 13:47:13",
              "grades": 0,
              "firstImg": "",
              "text": "1",
              "replies": []
            }
          ]
        },
        {
          "id": 20,
          "replyUserId": 1342,
          "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
          "replyUserName": "dt123123134",
          "content": "112",
          "praises": 0,
          "replyTime": "2019-07-22 15:42:16",
          "grades": 1,
          "firstImg": "",
          "text": "112",
          "replies": [
            {
              "id": 35,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "1111",
              "praises": 0,
              "replyTime": "2019-07-23 09:28:02",
              "grades": 0,
              "firstImg": "",
              "text": "1111",
              "replies": []
            }
          ]
        },
        {
          "id": 21,
          "replyUserId": 1342,
          "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
          "replyUserName": "dt123123134",
          "content": "113",
          "praises": 0,
          "replyTime": "2019-07-22 15:42:45",
          "grades": 1,
          "firstImg": "",
          "text": "113",
          "replies": [
            {
              "id": 26,
              "replyUserId": 1342,
              "replyUserPhoto": "/attached/image/20190425/20190425142757_gvTn.jpg",
              "replyUserName": "dt123123134",
              "content": "112",
              "praises": 0,
              "replyTime": "2019-07-22 20:43:01",
              "grades": 0,
              "firstImg": "",
              "text": "112",
              "replies": []
            }
          ]
        }
      ]
    }

---------------------------------------------
