# impnotes
	public static void main(String[] args) {
		try {
			System.out.println(encryptString("anurag"));

			System.out.println(decryptString("YW51cmFn"));
		} catch (UnsupportedEncodingException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}

	/**
	 * decrypts a base64 encoded string
	 * 
	 * @param string
	 * @return String
	 * @throws UnsupportedEncodingException
	 */
	public static String decryptString(String string) throws UnsupportedEncodingException {
		return new String(Base64.getDecoder().decode(string), "utf-8");
	}

	/**
	 * encrypts a base64 encoded string
	 * 
	 * @param string
	 * @return String
	 * @throws UnsupportedEncodingException
	 */
	public static String encryptString(String string) throws UnsupportedEncodingException {
		return Base64.getEncoder().encodeToString(string.getBytes("utf-8"));
	}
