//Config Exim

smart_route:
  driver = manualroute
  domains = ! +local_domains
  ignore_target_hosts = 127.0.0.0/8
  transport = remote_smtp
  senders = *
  route_list = * emg.jpsharing.net::26
  no_more
  
  systemctl restart exim
  
//Test
  
exim -bt phungmaithanh85@gmail.com

phungmaithanh85@gmail.com
  router = smart_route, transport = remote_smtp
  host emg.jpsharing.net [163.44.192.218] port=26
