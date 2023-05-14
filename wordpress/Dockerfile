FROM		php:fpm-buster

ENV		LD_LIBRARY_PATH ${LD_LIBRARY_PATH}:/usr/local/lib/

RUN			\
			# Update to latest
			apt -y update && \
			apt -y install default-mysql-client libmagickwand-dev libjpeg-progs optipng gifsicle libzip-dev && \
			pecl install apcu imagick && \
			echo "extension=apcu.so" > $PHP_INI_DIR/conf.d/apcu.ini && \
			docker-php-ext-install mysqli opcache bcmath exif zip intl && \
			docker-php-ext-enable mysqli opcache bcmath imagick exif zip intl && \
			echo "post_max_size=128M" >  $PHP_INI_DIR/conf.d/upload_size.ini && \
			echo "upload_max_filesize=128M" >> $PHP_INI_DIR/conf.d/upload_size.ini && \
			# Install cwebp from source code
			curl https://storage.googleapis.com/downloads.webmproject.org/releases/webp/libwebp-1.2.2.tar.gz --output /root/libwebp.tar.gz && \
			cd /root && tar zxf libwebp.tar.gz && \
			cd libwebp-1.2.2 && \
			./configure && make && make install && \
			cd /root && rm -rf libwebp-1.2.2 && rm -f libwebp.tar.gz && \
			# Done
			echo "Build complete."
