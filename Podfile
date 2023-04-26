platform :osx, '12.0'
use_frameworks!

target 'SpotMenu' do
    pod 'Sparkle'
    pod 'LoginServiceKit', :git => 'https://github.com/Clipy/LoginServiceKit.git'
end

# @WORKAROUND: Unable to build project in Xcode 14.3 due to missing arc dir 
# s. discussion about "missing arc dir" build-issue on Apple Developer Forums: https://developer.apple.com/forums/thread/725300
# s. background for the following post-install hook: https://github.com/CocoaPods/CocoaPods/issues/7314#issuecomment-355905199
post_install do |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['MACOSX_DEPLOYMENT_TARGET'] = '12.0'
        end
    end
end
