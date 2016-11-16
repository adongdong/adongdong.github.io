---
layout: post
title: tp基本的curd操作
category: tp
tag: [tp框架]
---

##tp基本的curd操作

     <?php
        // 本类由系统自动生成，仅供测试用途
        class IndexAction extends Action {
            public function index(){
                $user=M('User');
                $data = array(
                    'usernames' => 'php100',
                    'password' => md5('php200'),
                     );
                //成功则返回ID，失败则返回false,会过滤字段
                //echo $user->add($data);
                //直接用add也可以但是不会过滤字段
                echo $user->data($data)->add();
                echo $user->getLastSql();
            }
            //批量插入,字段必须一致
            public function addALL(){
                $user=M('User');
                $data=array(
                    array('usernames'=>'123','password'=>'aaa1'),
                    array('usernames'=>'456','password'=>'aaa2'),
                    array('usernames'=>'789','password'=>'aaa3'),
                    );
                dump($user->addALL($data));
            }
            //查询-select
            //查询所有符合条件的记录
            public function sel(){
                $user=M('User');
                //select()同样支持参数，比如输入10则为第10条
                $userlist=$user->where('id=10')->select();
                dump($userlist);
            }
            //查询-find
            //查询符合条件记录的第N调,默认为1
            public function find(){
                $user=M('User');
                //find()括号是可以给参数的比如10则读取第10条数据
                $userlist=$user->find();
                dump($userlist);
            }
            //查询-getfield
            public function getfield(){
                $user=M('user');
                //默认把第一个当成数组的下标,一般结合连贯操作
                //后跟数字6则只读取6条，
                $list=$user->getfield('id,usernames,password',6);
                print_r($list);
            }
            //更新save
            //返回的是影响的行数
            public function up(){
                $user=M('user');
                //下边的ID不一定为ID，一般为主键
                $data = array('usernames' =>'pog');
                $list = $user->where('id=10')->save($data);
                print_r($user->find(10));    //打印出第10条记录
                dump($list);
                //为下边的批量更新做准备
                $data=array(
                    array('usernames'=>'y123','password'=>'aaa1','id'=>'21'),
                    array('usernames'=>'y456','password'=>'aaa2','id'=>'22'),
                    array('usernames'=>'y789','password'=>'aaa3','id'=>'23'),
                    );
                    $this->upall($data);
                    dump($user->select());
            }
            //批量更新
            //自定义函数
            public function upall($arr){
                $user=M('user');
                foreach ($arr as $key => $value) {
                    $user->save($value);
                }
            }
            //更新字段 setfield
            public function setField()
            {
                $user=M('user');
                $data = array('password' => 'ok' );
                $user->where('id=20')->setField($data);
                dump($user->find(20));
            }
            //自增、自减
            //默认以1自增自减setInc setDec
            public function set(){
                $user=M('user');
                $user->where('id=25')->setDec('regtime',10);
                dump($user->find(25));
            }
            //数据删除方法 delete
            //小心操作id=3 一般为一条数据
            public function del(){
                $user=M('user');
                $user->where('id=3')->delete();
                dump($user->getField('id,usernames',5));
            }
        }