require 'rake'
require 'rubygems'
require './utils/log'
require 'pry'
namespace :vim do

  VIMRC_SOURCE = ENV['HOME']+ "/.vim-for-rails/.vimrc"
  VIMRC_PATH = ENV['HOME'] + "/.vimrc"
  VIMRC_BACKUP_PATH = VIMRC_PATH + "_backup"

  VIM_SOURCE = ENV['HOME'] + "/.vim-for-rails/.vim/"
  VIM_FOLDER_PATH = ENV['HOME'] + "/.vim"
  VIM_FOLDER_BACKUP_PATH = VIM_FOLDER_PATH + "_backup"

  task :welcome do
    Log.msg :green,'
  ====================
  Vim for Rails
  ====================

  Prepared by h4b0
  www site: http://h4b0.pl
  github repo: https://github.com/h4b00/vim-for-rails/
'
  Log.info "Starting installing Vim."
  end

  desc "Install vim"
  task :install, [:overwrite] do |t, args|
    Rake::Task['vim:welcome'].invoke
    force = args[:overwrite] == "force"
    Log.info "Overwriten mode!" if force
    exist = false

    # Symlink to vim folder
    if File.exists?(VIM_FOLDER_PATH) || File.symlink?(VIM_FOLDER_PATH)
      Log.warn "#{VIM_FOLDER_PATH} already exists"
      if force
        Log.info "Moved old #{VIM_FOLDER_PATH} to #{VIM_FOLDER_BACKUP_PATH}"
        FileUtils.mv VIM_FOLDER_PATH, VIM_FOLDER_BACKUP_PATH
        Log.info "Make symlink  #{VIM_FOLDER_PATH} to #{VIM_SOURCE}"
        FileUtils.ln_s VIM_SOURCE, VIM_FOLDER_PATH
      end
      exist = true
    else
      Log.info "Make symlink #{VIM_FOLDER} to #{VIM_SOURCE} "
      FileUtils.ln_s VIM_SOURCE, VIM_FOLDER_PATH 
    end

    # Symlink to vimrc
    if File.exists?(VIMRC_PATH) || File.symlink?(VIMRC_PATH)
      Log.warn "#{VIMRC_PATH} already exists!"
      if force
        Log.warn "Moved old .#{VIMRC_PATH} to #{VIMRC_BACKUP_PATH}"
        FileUtils.mv VIMRC_PATH, VIMRC_BACKUP_PATH
        Log.info "Make symlink #{VIMRC_SOURCE}  to #{VIMRC_PATH} "
        FileUtils.ln_s VIMRC_SOURCE, VIMRC_PATH
      end
      exist = true
    else
      Log.info "Make symlink #{VIMRC_PATH} to #{VIMRC_SOURCE}"
      FileUtils.ln_s VIMRC_SOURCE, VIMRC_PATH
    end

    if exist && !force
      Log.warn "You already have configuration files for vim."
      Log.warn "Anyway you can overwrite them, just run vim:install[force]"
      Log.warn "In overwrite mode we make backup for previous config, so don't worry."

    else

      %w(swap backup).each do |tmps|
        FileUtils.mkdir_p File.join(VIM_FOLDER_PATH, 'tmp', tmps)
      end
      Log.info 'Installing Plugins...'
      sleep 4
      if system('vim +PluginInstall +qall')
        Log.success "Its finish! "
      else
        Log.error "There was an error while installing Plugin."
      end
    end
  end
end
