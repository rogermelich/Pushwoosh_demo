<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="box box-primary direct-chat direct-chat-primary">
      <div class="box-header with-border">
        <h3 class="box-title">Direct Chat</h3>

        <div class="box-tools pull-right">
          <span data-toggle="tooltip" title="3 New Messages" class="badge bg-light-blue">3</span>
          <button type="button" class="btn btn-box-tool" data-widget="collapse"><i class="fa fa-minus"></i>
          </button>
          <button type="button" class="btn btn-box-tool" data-toggle="tooltip" title="Contacts" data-widget="chat-pane-toggle">
            <i class="fa fa-comments"></i></button>
          <button type="button" class="btn btn-box-tool" data-widget="remove"><i class="fa fa-times"></i></button>
        </div>
      </div>
      <!-- /.box-header -->
      <div class="box-body">
        <!-- Conversations are loaded here -->
        <div class="direct-chat-messages">
          <!-- Message. Default to the left -->
          <div class="direct-chat-msg">
            <div class="direct-chat-info clearfix">
              <span class="direct-chat-name pull-left">Alexander Pierce</span>
              <span class="direct-chat-timestamp pull-right">23 Jan 2:00 pm</span>
            </div>
            <!-- /.direct-chat-info -->
            <img class="direct-chat-img" src="../../bower_components/AdminLTE/dist/img/user1-128x128.jpg" alt="Message User Image"><!-- /.direct-chat-img -->
            <div class="direct-chat-text">
              Is this template really for free? That's unbelievable!
            </div>
            <!-- /.direct-chat-text -->
          </div>
            <!-- /.direct-chat-msg -->
      </div>
        </div>
    </div>
    <div class="box-footer">
      <form action="#" method="post">
        <div class="input-group">
          <input type="text" name="message" placeholder="Type Message ..." class="form-control">
          <span class="input-group-btn">
            <button v-on:clicked class="btn btn-primary btn-flat">Send</button>
          </span>
        </div>
      </form>
    </div>
    </div>
</template>

<script>
export default {
  data: function () {
    return {
      // note: changing this line won't causes changes
      // with hot-reload because the reloaded component
      // preserves its current state and we are modifying
      // its initial state.
      msg: 'Hello World!',
      notification: "Notification. .....",
      notification: []


  }
  },
  methods: {
    notify: function(){
      console.debug('Click OK');
      $.ajax({
        type: "POST",
        url: "https://cp.pushwoosh.com/json/1.3/createMessage",
        data: JSON.stringify({
          "request": {
            "application": "4FC89B6D14A655.46488481",
            "auth": "mTdns0j6qLYPa/A5htmD46xVyoxdVQfPBz7NRqYYHz9PhvKXgJtOkAY+yo0YTXDEoztQAJFY0JmXnd89tf59",
            "notifications": [{
              "send_date": "now",
              "ignore_user_timezone": true,
              "content": "Hello world!"
            }]
          }
        }),
        dataType: "json"
      }).done(function(data) {
        console.log(data);
      });
    }
  }
}
</script>
