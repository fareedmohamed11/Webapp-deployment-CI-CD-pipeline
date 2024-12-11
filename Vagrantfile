Vagrant.configure("2") do |config|
  
  # إعدادات الجهاز الأول
  config.vm.define "machine1" do |machine1|
    machine1.vm.box = "ubuntu/bionic64" # استخدم أي صورة تريدها
    machine1.vm.network "private_network", type: "dhcp"
    machine1.vm.provider "virtualbox" do |vb|
      vb.memory = "512" # 512 ميجابايت من الذاكرة
      vb.cpus = 1 # معالج واحد
    end
  end

  # إعدادات الجهاز الثاني
  config.vm.define "machine2" do |machine2|
    machine2.vm.box = "ubuntu/bionic64" # نفس صورة الجهاز الأول
    machine2.vm.network "private_network", type: "dhcp"
    machine2.vm.provider "virtualbox" do |vb|
      vb.memory = "512" # 512 ميجابايت من الذاكرة
      vb.cpus = 1 # معالج واحد
    end
  end
end
