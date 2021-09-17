FROM		php:fpm-buster

RUN			\
			# Update to latest
			apt -y update && \
			apt -y install default-mysql-client && \
			docker-php-ext-install mysqli && docker-php-ext-enable mysqli && \
			# Done
			echo "Build complete."
